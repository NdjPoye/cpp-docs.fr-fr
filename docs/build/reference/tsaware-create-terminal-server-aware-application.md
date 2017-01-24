---
title: "/TSAWARE (Cr&#233;er une application sensible &#224; Terminal Server) | Microsoft Docs"
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
  - "/tsaware"
  - "VC.Project.VCLinkerTool.TerminalServerAware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TSAWARE (option de l'éditeur de liens)"
  - "Terminal Server"
  - "Terminal Server, applications Terminal Server"
  - "TSAWARE (option de l'éditeur de liens)"
  - "-TSAWARE (option de l'éditeur de liens)"
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TSAWARE (Cr&#233;er une application sensible &#224; Terminal Server)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TSAWARE[:NO]  
```  
  
## Notes  
 L'option \/TSAWARE définit un indicateur dans le champ DllCharacteristics IMAGE\_OPTIONAL\_HEADER de l'en\-tête facultatif de l'image du programme.  Lorsque cet indicateur est défini, Terminal Server n'apporte pas certaines modifications à l'application.  
  
 Lorsqu'une application n'est pas compatible Terminal Server \(on parle alors d'application héritée ou legacy\), Terminal Server lui apporte des modifications pour la faire fonctionner correctement dans un environnement multi\-utilisateur.  Par exemple, il va créer un dossier Windows virtuel, de sorte que chaque utilisateur possède un dossier Windows au lieu d'utiliser le répertoire système Windows.  Les utilisateurs ont ainsi la possibilité d'accéder à leurs propres fichiers INI.  De plus, Terminal Server modifie quelque peu le Registre d'une application héritée \(legacy\).  Ces modifications ralentissent le chargement de l'application héritée \(legacy\) sur Terminal Server.  
  
 Si une application est compatible Terminal Server, elle ne doit ni s'appuyer sur les fichiers INI, ni écrire sur la clé de Registre **HKEY\_CURRENT\_USER** pendant la configuration.  
  
 Si vous utilisez \/TSAWARE et que votre application continue d'utiliser les fichiers INI, les fichiers seront partagés par tous les utilisateurs du système.  Si cela fonctionne, vous pouvez toujours lier votre application à l'aide de l'option \/TSAWARE ; sinon, vous devez utiliser \/TSAWARE:NO.  
  
 L'option \/TSAWARE est activée par défaut pour Windows 2000 et versions ultérieures, pour Windows et les applications de console.  Pour plus d'informations, consultez [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) et [\/VERSION](../../build/reference/version-version-information.md)  
  
 \/TSAWARE n'est pas valide pour les pilotes, les pilotes de périphériques virtuels \(VxD\) ou les DLL.  
  
 Si une application a été liée avec l'option \/TSAWARE, DUMPBIN [\/HEADERS](../../build/reference/headers.md) affichera des informations à cet effet.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Système**.  
  
4.  Modifiez la propriété **Terminal Server**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [Storing User\-Specific Information](http://msdn.microsoft.com/library/aa383452)   
 [Legacy Applications in a Terminal Services Environment](https://msdn.microsoft.com/en-us/library/aa382957.aspx)