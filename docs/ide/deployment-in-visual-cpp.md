---
title: "D&#233;ploiement dans Visual C++ | Microsoft Docs"
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
  - "déploiement d'applications (C++)"
  - "déployer des applications (C++)"
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;ploiement dans Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous déployez une application [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] sur un autre ordinateur, vous devez installer l'application et tous les fichiers bibliothèques desquels elle dépend.  Après la mise à jour d'une bibliothèque, par exemple en cas de correction d'une faille de sécurité , il est souhaitable que vous appliquiez la mise à jour partout où l'application est déployée.  
  
 Visual Studio offre trois manières de déployer les bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] avec votre application : déploiement centralisé, déploiement local et liaison statique.  Microsoft met automatiquement à jour les bibliothèques qui sont déployées de manière centralisée.  En ce qui concerne les bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] déployées localement ou liées statiquement, le rédacteur d'application doit fournir les mises à jour.  
  
## Déploiement central  
 Dans un déploiement centralisé, les fichiers de bibliothèque [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] sont installés dans le répertoire %windir%\\system32\\.  Pour déployer les bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] de manière centralisée, vous pouvez utiliser les :  
  
-   *fichiers du package redistribuable*, qui sont des exécutables autonomes de ligne de commande permettant d'installer les bibliothèques redistribuables [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
-   *modules de fusion redistribuables \(fichiers .msm\)*, utilisables pour déployer des bibliothèques spécifiques et que vous incluez dans le fichier Windows Installer de votre application \(.msi\).  
  
 Un fichier de package redistribuable installe les bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] spécifiques à une architecture système particulière.  Vous pouvez programmer votre installation d'application pour qu'elle s'exécute en tant que condition préalable à l'installation de celle\-ci.  Un module de fusion permet l'inclusion de la logique d'installation d'une bibliothèque [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] spécifique dans un fichier d'installation de Windows Installer.  Vous pouvez inclure autant de modules de fusion que l'application requiert.  
  
 Étant donné que le déploiement centralisé des bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] à l'aide d'un package redistribuable permet la mise à jour automatique par Microsoft, nous vous recommandons d'utiliser la liaison dynamique et les packages redistribuables pour votre application.  
  
## Déploiement local  
 Dans un déploiement local, les fichiers bibliothèques sont installés dans le dossier de l'application avec le fichier exécutable.  Différentes versions des bibliothèques peuvent être installées dans le même dossier parce que le nom de fichier de chaque version est rendu unique par l'inclusion de son numéro de version.  Par exemple, la version 12 de la bibliothèque Runtime C est msvcr120.dll.  
  
 Étant donné que Microsoft ne peut pas mettre à jour automatiquement les bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] déployées localement, nous déconseillons le déploiement local de celles\-ci.  Si vous décidez de recourir au déploiement local des bibliothèques redistribuables, nous vous recommandons d'appliquer votre propre méthode de mise à jour automatique des bibliothèques déployées localement.  
  
## Liaison statique  
 Vous pouvez lier statiquement une bibliothèque [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] à l'application, en d'autres termes, la compiler dans l'application, de façon à éviter de déployer les fichiers de bibliothèque [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] séparément.  Toutefois, nous déconseillons cette approche, car les bibliothèques liées statiquement ne peuvent pas être mises à jour sur place.  Si vous utilisez la liaison statique et souhaitez mettre à jour une bibliothèque liée, vous devez recompiler et redéployer votre application.  
  
## Résolution des problèmes  
 L'ordre de chargement des bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] dépend du système.  Pour diagnostiquer des problèmes liés au chargeur, utilisez depends.exe ou where.exe.  Pour plus d'informations, consultez [Dynamic\-Link Library Search Order \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).  
  
## Voir aussi  
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)