---
description: Analisa um script serializado e retorna uma função que representa o script. Fornece a capacidade de carregar a fonte de script somente se/quando for necessária.
title: Função JsParseSerializedScriptWithCallback | Documentos da Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 0315fa82201671fc0ef0c950ef05a14a26be114e
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752238"
---
# Função JsParseSerializedScriptWithCallback
Analisa um script serializado e retorna uma função que representa o script. Fornece a capacidade de carregar a fonte de script somente se/quando for necessária.  
  
## Sintaxe  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_ JsValueRef * result  
);  
  
```  
  
#### Parâmetros  
 `scriptLoadCallback`  
 Retorno de chamada chamado quando o código-fonte do script precisa ser carregado.  
  
 `scriptUnloadCallback`  
 Retorno de chamada chamado quando o script serializado e o código-fonte não são mais necessários.  
  
 `buffer`  
 O script serializado.  
  
 `sourceContext`  
 Um cookie identificando o script que pode ser usado por contextos de script debuggable.     Esse contexto passará para scriptLoadCallback e scriptUnloadCallback.  
  
 `sourceUrl`  
 O local de onde o script veio.  
  
 `result`  
 Uma função que representa o código de script.  
  
## Valor de retorno  
 O código `JsNoError` se a operação tiver sido bem-sucedida, um código de falha também.  
  
## Comentários  
  
> [!NOTE]
>  Esta API ainda não está disponível para aplicativos da loja.  
  
 Requer um contexto de script ativo.  
  
 O tempo de execução será armazenado no buffer até que todas as instâncias criadas do buffer sejam coletadas como lixo.  Em seguida, ele chamará scriptUnloadCallback para informar ao chamador que é seguro liberar.  
  
## Requisitos  
 **Header:** jsrt. h  
  
## Consulte também  
 [Referência (Runtime do JavaScript)](../chakra-hosting/reference-javascript-runtime.md)