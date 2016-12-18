---
title: "/SECTION (EDITBIN) | Microsoft Docs"
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
  - "/section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SECTION (option Editbin)"
  - "caractères d'alignement dans les sections"
  - "SECTION (option Editbin)"
  - "-SECTION (option Editbin)"
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SECTION (EDITBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## Notes  
 Cette option modifie les attributs d'une section, en substituant les attributs qui ont été définis lors de la compilation ou de la liaison du fichier objet de la section.  
  
 Après deux\-points \(**:**\), spécifiez l'argument *name* de la section.  Pour modifier le nom de la section, faites suivre *name* du signe égal à \(\=\) et d'un *newname* pour la section.  
  
 Pour définir ou modifier les `attributes` de la section, spécifiez une virgule \(**,**\) suivie d'un ou de plusieurs caractères des attributs.  Pour inverser l'effet d'un attribut, faites précéder son caractère d'un point d'exclamation \(\!\).  Les caractères suivants spécifient des attributs de mémoire :  
  
|Attribut|Paramètre|  
|--------------|---------------|  
|c|code|  
|d|discardable \(peut être supprimé\)|  
|e|exécutable|  
|i|initialized data \(données initialisées\)|  
|k|cached virtual memory \(mémoire virtuelle en cache\)|  
|m|link remove \(suppression de la liaison\)|  
|o|link info \(informations sur la liaison\)|  
|p|paged virtual memory \(mémoire virtuelle paginée\)|  
|r|read \(lecture\)|  
|s|shared|  
|u|uninitialized data \(données non initialisées\)|  
|w|write \(écriture\)|  
  
 Pour déterminer l'alignement \(*alignment*\), spécifiez le caractère **A** suivi d'un des caractères suivants pour définir la taille de l'alignement en octets, comme ci\-dessous :  
  
|Caractère|Taille de l'alignement en octets|  
|---------------|--------------------------------------|  
|1|1|  
|2|2|  
|4|4|  
|8|8|  
|p|16|  
|t|32|  
|s|64|  
|x|pas d'alignement|  
  
 Spécifiez les caractères des arguments `attributes` et *alignment* en tant que chaîne sans espace blanc.  Les caractères ne respectent pas la casse.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)