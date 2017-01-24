---
title: "Avertissement des outils &#201;diteur de liens LNK4210 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4210"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4210"
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4210
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la section 'section' existe ; il se peut qu'il y ait des terminateurs ou des initialiseurs static non gérés  
  
 Du code a introduit des initialiseurs ou terminateurs statiques, mais le CRT ou son équivalent \(qui doit les exécuter\) n'est pas exécuté au démarrage de l'application.  Voici quelques exemples de code qui provoqueraient cette situation :  
  
-   Une variable de classe globale avec une table de constructeurs, de destructeurs ou de fonctions virtuelles.  
  
-   Une variable globale initialisée avec une constante à un moment autre que lors de la compilation.  
  
 Pour résoudre ce problème, essayez l'une des actions suivantes :  
  
-   Supprimez tout le code contenant des initialiseurs statiques.  
  
-   N'utilisez pas [\/NOENTRY](../../build/reference/noentry-no-entry-point.md).  Une fois \/NOENTRY supprimé, vous devrez peut\-être également ajouter msvcrt.lib, libcmt.lib ou libcmtd.lib à votre ligne de commande de l'éditeur de liens.  
  
-   Ajoutez msvcrt.lib, libcmt.lib ou libcmtd.lib à votre ligne de commande de l'éditeur de liens.  
  
-   Lors du déplacement de la compilation \/clr:pure vers \/clr, supprimez l'option [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) de la ligne de l'éditeur de liens.  L'initialisation du CRT est alors activée et permet l'exécution des initialiseurs statiques au démarrage de l'application.  
  
-   Si votre projet est généré avec [\/ENTRY](../../build/reference/entry-entry-point-symbol.md), et si une fonction autre que `_DllMainCRTStartup` est passée à \/ENTRY, la fonction doit appeler CRT\_INIT.  Consultez [Comportement de la bibliothèque d'exécutables](../../build/run-time-library-behavior.md) et l'article Q94248 de la Base de connaissances, [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;94248](http://support.microsoft.com/default.aspx?scid=kb;en-us;94248) pour plus d'informations.  
  
 L'option du compilateur [\/GS](../../build/reference/gs-buffer-security-check.md) requiert du code de démarrage CRT.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)