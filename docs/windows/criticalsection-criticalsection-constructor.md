---
title: "CriticalSection::CriticalSection, constructeur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection, constructeur"
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSection::CriticalSection, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise un objet de synchronisation semblable à un objet de mutex, mais peut être utilisé uniquement par les threads d'un processus unique.  
  
## Syntaxe  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### Paramètres  
 `spincount`  
 Le compteur de rotations pour l'objet de la section critique.  La valeur par défaut est 0.  
  
## Remarques  
 Pour plus d'informations sur les sections critiques et les compteurs de rotations, consultez la fonction **InitializeCriticalSectionAndSpinCount** dans la section Synchronisation de la documenation de l'API Windows.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [CriticalSection, classe](../windows/criticalsection-class.md)