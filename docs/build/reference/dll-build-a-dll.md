---
title: "/DLL (G&#233;n&#233;rer une DLL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DLL (option de l'éditeur de liens C++)"
  - "-DLL (option de l'éditeur de liens)"
  - "DLL (option de l'éditeur de liens C++)"
  - "DLL (C++), générer"
  - "exporter des DLL (C++), spécifier des exportations"
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /DLL (G&#233;n&#233;rer une DLL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DLL  
```  
  
## Notes  
 L'option \/DLL génère une DLL comme fichier de sortie principal.  Une DLL contient en général les exportations utilisables par un autre programme.  Il existe trois méthodes de spécification des exportations, présentées dans l'ordre d'utilisation recommandé :  
  
1.  [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) dans le code source ;  
  
2.  une instruction [EXPORTS](../../build/reference/exports.md) dans un fichier .def ;  
  
3.  une spécification [\/EXPORT](../../build/reference/export-exports-a-function.md) dans une commande LINK.  
  
 Un programme peut utiliser plusieurs méthodes.  
  
 Une autre façon de générer une DLL consiste à utiliser l'instruction de définition de module **LIBRARY**.  Les options \/BASE et \/DLL réunies sont équivalentes à l'instruction **LIBRARY**.  
  
 Ne spécifiez pas uniquement cette option sur la ligne de commande ; il ne faut donc pas l'utiliser dans l'environnement de développement.  Cette option est définie lorsque vous créez un projet DLL avec un Assistant Application.  
  
 Notez que si vous créez votre bibliothèque d'importation lors d'une étape préliminaire, avant de créer votre fichier .dll, vous devez passer lors de la génération du fichier .dll le même jeu de fichiers objets que celui que vous avez passé lors de la génération de la bibliothèque d'importation.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Propriétés de configuration**.  
  
3.  Cliquez sur la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Type de configuration**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)