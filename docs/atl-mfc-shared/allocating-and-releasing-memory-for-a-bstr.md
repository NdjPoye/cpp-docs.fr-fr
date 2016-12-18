---
title: "Allocating and Releasing Memory for a BSTR | Microsoft Docs"
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
  - "bstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR, allocation de mémoire"
  - "mémoire (C++), libération"
  - "allocation de mémoire, BSTR"
  - "memory deallocation, BSTR memory"
  - "memory deallocation, string memory"
  - "chaînes (C++), libération"
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Allocating and Releasing Memory for a BSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez `BSTR`s et les passez entre les objets COM, vous devez prendre en charge le traitement de la mémoire qu'ils utilisent pour éviter des fuites de mémoire.  Lorsque `BSTR` reste dans une interface, vous devez libérer la mémoire lorsque vous avez terminé avec elle.  Toutefois, lorsque `BSTR` passe hors d'une interface, l'objet de réception accepte la responsabilité de sa gestion de la mémoire.  
  
 En général les règles pour allouer et libérer la mémoire allouée pour `BSTR`s sont les suivantes :  
  
-   Lorsque vous appelez une fonction qui attend un argument d' `BSTR` , vous devez allouer de la mémoire pour `BSTR` avant l'appel et la libération après.  Par exemple :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   Lorsque vous appelez une fonction qui retourne `BSTR`, vous devez libérer la chaîne vous\-même.  Par exemple :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   Lorsque vous implémentez une fonction qui retourne `BSTR`, allouez la chaîne mais ne libérez pas la.  Recevoir la fonction libère la mémoire.  Par exemple :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## Voir aussi  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)   
 [SysAllocString](http://msdn.microsoft.com/fr-fr/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b)   
 [SysFreeString](http://msdn.microsoft.com/fr-fr/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3)