---
title: "space_info, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::space_info"
dev_langs: 
  - "C++"
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# space_info, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contient des informations sur un volume.  
  
## Syntaxe  
  
```  
struct space_info;  
```  
  
## Membres  
  
### Membres de données publics  
  
|Nom|Description|  
|---------|-----------------|  
|`unsigned long long available`|Représente le nombre d’octets qui sont disponibles pour représenter des données sur le volume.|  
|`unsigned long long capacity`|Représente le nombre total d’octets que le volume peut représenter.|  
|`unsigned long long free`|Représente le nombre d’octets qui ne sont pas utilisés pour représenter des données sur le volume.|  
  
## Configuration requise  
 **En\-tête :** filesystem  
  
 **Espace de noms :** std::tr2::sys  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)   
 [space, fonction](http://msdn.microsoft.com/fr-fr/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md)