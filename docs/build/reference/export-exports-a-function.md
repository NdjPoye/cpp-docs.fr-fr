---
title: "/EXPORT (Exporter une fonction) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ExportFunctions"
  - "/export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXPORT (option de l'éditeur de liens)"
  - "EXPORT (option de l'éditeur de liens)"
  - "-EXPORT (option de l'éditeur de liens)"
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /EXPORT (Exporter une fonction)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## Notes  
 Avec cette option, vous pouvez exporter une fonction à partir de votre programme afin de permettre à d'autres programmes de l'appeler.  Vous pouvez également exporter des données.  Les exportations sont généralement définies dans une DLL.  
  
 L'argument *entryname* est le nom de la fonction ou de l'élément de données tel qu'il doit être utilisé par le programme appelant.  `ordinal` spécifie un index dans la table d'exportations qui est compris entre 1 et 65 535 ; si vous ne spécifiez pas `ordinal`, LINK assigne la valeur 1.  Le mot clé **NONAME** exporte la fonction uniquement comme ordinal, sans *entryname*.  
  
 Le mot clé **DATA** spécifie que l'élément exporté est un élément de données.  L'élément de données du programme client doit être déclaré à l'aide de **extern \_\_declspec\(dllimport\)**.  
  
 Il existe trois méthodes d'exportation d'une définition, présentées dans l'ordre recommandé pour leur utilisation :  
  
1.  [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) dans le code source ;  
  
2.  une instruction [EXPORTS](../../build/reference/exports.md) dans un fichier .def ;  
  
3.  une spécification \/EXPORT dans une commande LINK.  
  
 Les trois méthodes peuvent être utilisées dans le même programme.  Quand LINK génère un programme contenant des exportations, il crée également une bibliothèque d'importation, sauf si un fichier .exp est utilisé lors de la génération.  
  
 LINK utilise les formes décorées des identificateurs.  Le compilateur décore un identificateur lorsqu'il crée le fichier .obj.  Si l'argument *entryname* est spécifié dans l'éditeur de liens sous sa forme non décorée \(tel qu'il apparaît dans le code source\), LINK tente d'établir une correspondance avec le nom.  En l'absence de correspondance unique, LINK émet un message d'erreur.  Utilisez l'outil [DUMPBIN](../../build/reference/dumpbin-reference.md) pour obtenir la forme de [Noms décorés](../../build/reference/decorated-names.md) d'un identificateur lorsque vous devez le spécifier à l'éditeur de liens.  
  
> [!NOTE]
>  Ne spécifiez pas la forme décorée des identificateurs en langage C qui sont déclarés sous la forme `__cdecl` ou `__stdcall`.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)