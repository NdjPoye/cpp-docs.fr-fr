---
title: "ComPtrRef::operator void**, op&#233;rateur | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator void**"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "void** (opérateur)"
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::operator void**, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
operator void**() const;  
```  
  
## Notes  
 Supprime l'objet ComPtrRef actuel, caste le pointeur vers l'interface représentée par l'objet ComPtrRef comme un pointeur\-vers\-pointeur\-vers `void`, puis retourne le pointeur de cast.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [ComPtrRef, classe](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)