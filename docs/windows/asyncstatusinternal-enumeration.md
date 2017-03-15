---
title: "AsyncStatusInternal, &#233;num&#233;ration | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::Details::AsyncStatusInternal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncStatusInternal (énumération)"
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncStatusInternal, &#233;num&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
enum AsyncStatusInternal;  
```  
  
## Notes  
 Spécifie un mappage entre les énumérations internes pour l'état des opérations asynchrones et l'énumération **Windows::Foundation::AsyncStatus**.  
  
## Membres  
 `_Created`  
 Équivalent à ::Windows::Foundation::AsyncStatus::Created  
  
 `_Started`  
 Équivalent à ::Windows::Foundation::AsyncStatus::Started  
  
 `_Completed`  
 Équivalent à ::Windows::Foundation::AsyncStatus::Completed  
  
 `_Cancelled`  
 Équivalent à ::Windows::Foundation::AsyncStatus::Cancelled  
  
 `_Error`  
 Équivalent à ::Windows::Foundation::AsyncStatus::Error  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)