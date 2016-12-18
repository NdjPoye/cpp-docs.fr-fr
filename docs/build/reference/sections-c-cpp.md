---
title: "SECTIONS (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SECTIONS (instruction de fichier .def)"
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# SECTIONS (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Introduit une section qui contient une ou plusieurs `definitions` représentant des spécificateurs d'accès dans des sections du fichier de sortie de votre projet.  
  
```  
SECTIONS  
definitions  
```  
  
## Notes  
 Chaque définition doit se trouver sur une ligne distincte.  Le mot clé `SECTIONS` peut figurer sur la même ligne que la première définition ou sur une ligne précédente.  Le fichier .def peut contenir une ou plusieurs instructions `SECTIONS`.  
  
 Cette instruction `SECTIONS` définit les attributs d'une ou de plusieurs sections du fichier image, et peut être utilisée pour substituer les attributs par défaut pour chaque type de section.  
  
 L'argument `definitions` a le format suivant :  
  
 `.section_name specifier`  
  
 où `.section_name` désigne le nom d'une section dans l'image du programme et `specifier`un ou plusieurs des modificateurs d'accès suivants :  
  
|Modificateur|Description|  
|------------------|-----------------|  
|`EXECUTE`|La section est exécutable.|  
|`READ`|Permet les opérations de lecture sur les données.|  
|`SHARED`|Partage la section parmi tous les processus qui chargent l'image.|  
|`WRITE`|Permet les opérations d'écriture sur les données.|  
  
 Séparez les noms des spécificateurs par un espace.  Par exemple :  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS` marque le début d'une liste de section `definitions`.  Chaque `definition` doit se trouver sur une ligne distincte.  Le mot clé `SECTIONS` peut être sur la même ligne que le premier `definition` ou sur une ligne précédente.  Le fichier .def peut contenir une ou plusieurs instructions `SECTIONS`.  Le mot clé `SEGMENTS` est pris en charge en tant que synonyme de `SECTIONS`.  
  
 Les versions antérieures de Visual C\+\+ prenaient en charge la syntaxe suivante :  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 Le mot clé `CLASS` est pris en charge à des fins de compatibilité, tout en étant ignoré.  
  
 Vous pouvez spécifier des attributs de section de manière équivalente à l'aide de l'option [\/SECTION](../../build/reference/section-specify-section-attributes.md).  
  
## Voir aussi  
 [Règles s'appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)