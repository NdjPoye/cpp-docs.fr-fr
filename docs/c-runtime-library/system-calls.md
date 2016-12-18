---
title: "Appels syst&#232;me | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.system"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "appels du système"
  - "Windows (C++), appels du système"
ms.assetid: 0255f2ec-a5a0-487e-8b09-9dad001d81ed
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Appels syst&#232;me
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions suivantes sont des appels système d'exploitation Windows.  
  
### Fonctions d'appel système  
  
|Fonction|Utilisez|Équivalent de .NET Framework|  
|--------------|--------------|----------------------------------|  
|[\_findclose](../c-runtime-library/reference/findclose.md)|Ressources de version des opérations de recherche précédentes|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_findfirst, \_findfirst32, \_findfirst64, \_findfirsti64, \_findfirst32i64, \_findfirst64i32, \_wfindfirst, \_wfindfirst32, \_wfindfirst64, \_wfindfirsti64, \_wfindfirst32i64, \_wfindfirst64i32](../c-runtime-library/reference/findfirst-functions.md)|Fichier de recherche avec les attributs spécifiés|[\<caps:sentence id\="tgt12" sentenceid\="e22cfa910fbeac637b6aba4ed3f9dc48" class\="tgtSentence"\>System::IO::DirectoryInfo::GetFiles\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.getfiles.aspx)|  
|[\_findnext, \_findnext32, \_findnext64, \_findnexti64, \_findnext32i64, \_findnext64i32, \_wfindnext, \_wfindnext32, \_wfindnexti64, \_wfindnext64, \_wfindnexti64](../c-runtime-library/reference/findnext-functions.md)|Fichier de recherche avec les attributs spécifiés|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Gestion de fichiers](../c-runtime-library/file-handling.md)   
 [Contrôle de répertoire](../c-runtime-library/directory-control.md)   
 [E\/S niveau bas](../c-runtime-library/low-level-i-o.md)