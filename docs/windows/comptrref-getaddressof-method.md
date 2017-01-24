---
title: "ComPtrRef::GetAddressOf, m&#233;thode | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddressOf (méthode)"
ms.assetid: 797df323-a2fa-412b-ab60-32cce3721096
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRef::GetAddressOf, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
InterfaceType* const * GetAddressOf() const;  
```  
  
## Valeur de retour  
 Adresse d'un pointeur vers l'interface représentée par l'objet ComPtrRef actuel.  
  
## Notes  
 Récupère l'adresse d'un pointeur vers l'interface représentée par l'objet ComPtrRef objet.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [ComPtrRef, classe](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)