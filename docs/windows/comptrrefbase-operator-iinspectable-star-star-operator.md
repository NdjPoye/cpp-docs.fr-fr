---
title: "ComPtrRefBase::operator IInspectable**, op&#233;rateur | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IInspectable** (opérateur)"
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRefBase::operator IInspectable**, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
operator IInspectable**() const;  
```  
  
## Remarques  
 Caste la donnée membre [ptr\_](../windows/comptrrefbase-ptr-data-member.md) actuelle en un pointeur\-vers\-un\-pointeur vers l'interface IInspectable.  
  
 Une erreur est émise si le ComPtrRefBase actuel ne dérive pas d'IInspectable.  
  
 Ce cast est disponible uniquement si **\_\_WRL\_CLASSIC\_COM\_\_** est défini.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [ComPtrRefBase, classe](../windows/comptrrefbase-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)