---
description: Uma referência a um objeto pertencente ao coletor de lixo Chakra.
title: Typedef JsRef | Documentos da Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f5ce1ada67a4530ba57345b90c0b7deba6954c7c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562139"
---
# Typedef JsRef
Uma referência a um objeto pertencente ao coletor de lixo Chakra.  
  
## Sintaxe  
  
```cpp  
typedef void *JsRef;  
```  
  
## Comentários  
 Um tempo de execução do Chakra automaticamente controlará as referências do JsRef desde que elas estejam armazenadas em variáveis locais ou em parâmetros (ou seja, na pilha). Armazenar um JsRef em outro lugar diferente de na pilha requer chamar JsAddRef e JsRelease para gerenciar o tempo de vida do objeto, caso contrário, o coletor de lixo pode liberar o objeto enquanto ele ainda está em uso.  
  
## Requisitos  
 **Header:** jsrt. h  
  
## Consulte também  
 [Referência (tempo de execução JavaScript)](../chakra-hosting/reference-javascript-runtime.md)