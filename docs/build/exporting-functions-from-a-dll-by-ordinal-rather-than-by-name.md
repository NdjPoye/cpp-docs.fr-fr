---
title: "Exportation de fonctions &#224; partir d&#39;une DLL par ordinal plut&#244;t que par nom | Microsoft Docs"
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
  - "NONAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exporter des DLL (C++), valeurs ordinales"
  - "exporter des fonctions (C++), valeurs ordinales"
  - "NONAME (attribut)"
  - "exportations par ordinal (C++)"
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exportation de fonctions &#224; partir d&#39;une DLL par ordinal plut&#244;t que par nom
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le moyen le plus simple d'exporter des fonctions à partir d'une DLL est de les exporter par nom.  C'est ce qui se passe lorsque vous utilisez **\_\_declspec\(dllexport\)**, par exemple.  Vous pouvez aussi exporter des fonctions par ordinal.  Avec cette technique, vous devez utiliser un fichier .def à la place de **\_\_declspec\(dllexport\)**.  Pour spécifier une valeur ordinale d'une fonction, annexez son ordinal au nom de la fonction dans le fichier .def.  Pour plus d'informations sur la spécification des ordinaux, consultez [Exportation à partir d'une DLL à l'aide de fichiers .def](../build/exporting-from-a-dll-using-def-files.md).  
  
> [!TIP]
>  Si vous souhaitez optimiser la taille de fichier de votre DLL, utilisez l'attribut **NONAME** pour chaque fonction exportée.  Avec l'attribut **NONAME**, les ordinaux sont stockés dans la table d'exportations de la DLL à la place des noms de fonctions.  Cela peut représenter une économie considérable si vous exportez de nombreuses fonctions.  
  
## Que voulez\-vous faire ?  
  
-   [Utiliser un fichier .def pour pouvoir effectuer une exportation par ordinal](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Utiliser \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## Voir aussi  
 [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)