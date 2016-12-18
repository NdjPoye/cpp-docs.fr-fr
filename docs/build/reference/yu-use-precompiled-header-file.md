---
title: "/Yu (Utiliser un fichier d&#39;en-t&#234;te pr&#233;compil&#233;) | Microsoft Docs"
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
  - "/yu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch, utiliser l'existant"
  - "/Yu (option du compilateur C++)"
  - "fichiers PCH, utiliser l'existant"
  - "fichiers d'en-tête précompilés, utiliser l'existant"
  - "Yu (option du compilateur C++)"
  - "-Yu (option du compilateur C++)"
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yu (Utiliser un fichier d&#39;en-t&#234;te pr&#233;compil&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prescrit au compilateur d'utiliser un fichier d'en\-tête précompilé \(.pch\) existant dans la compilation actuelle.  
  
## Syntaxe  
  
```  
/Yu[filename]  
```  
  
## Arguments  
 *filename*  
 Nom d'un fichier d'en\-tête, qui est inclus dans le fichier source à l'aide d'une directive de préprocesseur **\#include**.  
  
## Notes  
 Le nom du fichier Include doit être le même à la fois pour l'option **\/Yc** qui crée l'en\-tête précompilé et pour toute option **\/Yu** ultérieure indiquant l'utilisation de l'en\-tête précompilé.  
  
 Pour **\/Yc**, `filename` spécifie le point auquel la précompilation s'arrête ; le compilateur précompile tout le code jusqu'à `filename` et nomme l'en\-tête précompilé qui en résulte en utilisant le nom de base du fichier Include et une extension .pch.  
  
 Le fichier .pch a dû être créé avec **\/Yc**.  
  
 Le compilateur considère tout le code qui précède le fichier .h comme étant précompilé.  Il passe directement au code situé juste après la directive **\#include** associée au fichier .h, utilise le code contenu dans le fichier .pch, puis compile tout le code qui se trouve après `filename`.  
  
 Sur la ligne de commande, aucun espace n'est admis entre **\/Yu** et `filename`.  
  
 Si vous spécifiez l'option **\/Yu** sans un nom de fichier, votre programme source doit contenir un pragma [\#pragma hdrstop](../../preprocessor/hdrstop.md) qui spécifie le nom de fichier de l'en\-tête précompilé, le fichier .pch.  Dans ce cas, le compilateur utilise l'en\-tête précompilé \(fichier .pch\) nommé par [\/Fp \(Nom de fichier .pch\)](../../build/reference/fp-name-dot-pch-file.md).  Le compilateur passe directement à l'emplacement de ce pragma, restaure l'état compilé à partir du fichier d'en\-tête précompilé spécifié par le pragma, puis compile uniquement le code qui suit le pragma.  Si **\#pragma hdrstop** ne spécifie pas un nom de fichier, le compilateur recherche un fichier portant un nom dérivé du nom de base du fichier source avec une extension .pch.  Vous pouvez également utiliser l'option **\/Fp** pour spécifier un fichier .pch différent.  
  
 Si vous spécifiez l'option **\/Yu** sans nom de fichier et oubliez de spécifier un pragma **hdrstop**, un message d'erreur est généré et la compilation échoue.  
  
 Si les options **\/Yc**`filename` et  **\/Yu**`filename` se produisent sur la même ligne de commande et font toutes les deux référence au même nom de fichier, **\/Yc**`filename` prend la priorité, en précompilant tout le code jusqu'au fichier nommé compris.  Cette fonctionnalité simplifie l'écriture de makefiles.  
  
 Comme les fichiers .pch contiennent des informations relatives à l'environnement d'ordinateur, ainsi que des informations d'adresse mémoire à propos du programme, vous ne devez utiliser un fichier .pch que sur l'ordinateur où il a été créé.  
  
 Pour plus d'informations sur les en\-têtes précompilés, consultez :  
  
-   [\/Y \(En\-têtes précompilés\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Spécifiez [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md) sur un fichier .cpp contenu dans votre projet.  
  
2.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
3.  Cliquez sur le dossier **C\/C\+\+**.  
  
4.  Cliquez sur la page de propriétés **En\-têtes précompilés**.  
  
5.  Modifiez la propriété **Création\/utilisation d'un en\-tête précompilé en spécifiant un nom de fichier** ou la propriété **Création\/utilisation d'un en\-tête précompilé**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## Exemples  
 Si le code suivant :  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 est compilé avec la ligne de commande `CL /YuMYAPP.H PROG.CPP`, le compilateur ne traite pas les trois instructions Include, mais utilise le code précompilé du fichier MYAPP.pch ; la compilation est donc plus rapide puisque le compilateur n'a pas besoin de prétraiter les trois fichiers \(et les fichiers éventuels qu'ils peuvent inclure\).  
  
 Vous pouvez utiliser l'option [\/Fp \(Nom de fichier .pch\)](../../build/reference/fp-name-dot-pch-file.md) avec l'option **\/Yu** pour spécifier le nom du fichier .pch si le nom est différent de l'argument du nom de fichier de **\/Yc** ou du nom de base du fichier source, comme dans l'exemple ci\-dessous :  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 Cette commande spécifie un fichier d'en\-tête précompilé, nommé MYPCH.pch.  Le compilateur utilise son contenu pour restaurer l'état précompilé de tous les fichiers d'en\-tête jusqu'à MYAPP.h \(inclus\).  Le compilateur compile ensuite le code se trouvant après l'instruction **include** MYAPP.h.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)