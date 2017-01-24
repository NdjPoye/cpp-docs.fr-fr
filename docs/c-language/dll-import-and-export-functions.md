---
title: "Fonctions d&#39;importation et d&#39;exportation de DLL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "déclarer des fonctions, avec dllexport et dllimport"
  - "exportations de DLL (C++)"
  - "dllexport (attribut) (C++), attribut de classe de stockage"
  - "dllimport (attribut) (C++), attribut de classe de stockage"
  - "DLL (C++), importer"
  - "attributs de classe de stockage étendue"
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions d&#39;importation et d&#39;exportation de DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les informations les plus complètes et récentes à ce sujet se trouvent dans la rubrique [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 Les modificateurs de classe de stockage **dllimport** et `dllexport` sont des extensions spécifiques à Microsoft pour le langage C.  Ces modificateurs définissent explicitement l'interface de la DLL à son client \(le fichier exécutable ou une autre DLL\).  La déclaration de fonctions comme `dllexport` élimine le besoin d'utiliser un fichier de définition de module \(.DEF\).  Vous pouvez également utiliser les modificateurs **dllimport** et `dllexport` avec des données et des objets.  
  
 Les modificateurs de classe de stockage **dllimport** et `dllexport` doivent être utilisés avec le mot clé de syntaxe à attributs étendus, `__declspec`, comme indiqué dans l'exemple suivant :  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllExport int j;  
DllExport int n;  
```  
  
 Pour obtenir des informations spécifiques sur la syntaxe des modificateurs étendus de classe de stockage, consultez [Attributs étendus de classe de stockage](../c-language/c-extended-storage-class-attributes.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Définitions de fonction C](../c-language/c-function-definitions.md)