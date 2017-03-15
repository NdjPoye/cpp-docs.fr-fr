---
title: "Redistribution des composants &#224; l&#39;aide de modules de fusion | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modules de fusion, utiliser"
  - "redistribuer des applications, utiliser des modules de fusion"
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Redistribution des composants &#224; l&#39;aide de modules de fusion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] inclut des [modules de fusion](http://msdn.microsoft.com/library/aa367434) pour chaque composant [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] autorisé à être redistribué par une application.  Lorsqu'un module de fusion est compilé dans un fichier d'installation de Windows Installer, il permet le déploiement de certaines DLL sur des ordinateurs comportant une plateforme spécifique.  Dans votre fichier d'installation, indiquez que les modules de fusion sont des composants requis pour votre application.  Lors de l'installation de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], les modules de fusion sont installés dans \\Program Files\\Common Files\\Merge Modules\\. \(Uniquement des versions sans débogage des DLL [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] peuvent être redistribuées.\) Pour obtenir plus d'informations et un lien vers une liste des modules de fusion autorisés à la redistribution, consultez [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md).  
  
 Vous pouvez utiliser des modules de fusion pour permettre l'installation des DLL redistribuables [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] dans le dossier %SYSTEMROOT%\\system32\\. \([!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] lui\-même utilise cette technique.\) Toutefois, l'installation dans ce dossier échouera à moins que l'utilisateur chargé de l'installation possède des droits d'administrateur.  
  
 Nous vous déconseillons d'utiliser des modules de fusion à moins que vous n'ayez pas à assurer la maintenance de votre application et qu'il n'existe pas de dépendances sur plus d'une version des DLL.  Les modules de fusion applicables à différentes versions de la même DLL ne peuvent être inclus dans un programme d'installation. De plus, les modules de fusion rendent difficile la maintenance des DLL indépendamment de l'application.  À la place, nous vous recommandons d'installer un package redistribuable [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
## Voir aussi  
 [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md)