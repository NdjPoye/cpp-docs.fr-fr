---
title: "Fonctionnement des d&#233;pendances d&#39;une application Visual C++ | Microsoft Docs"
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
  - "déploiement d'applications (C++), dépendances"
  - "dépendances (C++), déploiement d'applications et"
  - "Dependency Walker"
  - "depends.exe"
  - "déployer des applications (C++), dépendances"
  - "DLL (C++), dépendances"
  - "DUMPBIN (utilitaire)"
  - "bibliothèques (C++), problèmes de déploiement d'applications"
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctionnement des d&#233;pendances d&#39;une application Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour déterminer les bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] dont dépend une application, vous pouvez afficher les propriétés du projet.  \(Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le projet, puis choisissez **Propriétés** pour ouvrir la boîte de dialogue **Pages de propriétés**.\) Vous pouvez également utiliser le Dependency Walker \(depends.exe\), qui donne une image plus complète des dépendances.  
  
 Dans la boîte de dialogue **Pages de propriétés**, vous pouvez examiner différentes pages sous **Propriétés de configuration** pour comprendre les dépendances.  Par exemple, si votre projet utilise les bibliothèques MFC et que vous choisissez **Utilisation des MFC**, **Utiliser les MFC dans une DLL partagée** dans la page **Propriétés de configuration**, **Général**, votre application au moment de l'exécution dépend de DLL MFC telles que mfc\<version\>.dll.  Si votre application n'utilise pas MFC, elle peut encore dépendre de la bibliothèque CRT si vous choisissez pour la **Bibliothèque Runtime** une valeur de **DLL de débogage multithread \(\/MDd\)** ou de **DLL multithread \(\/MD\)** sur la page **Propriétés de configuration**, **C\/C\+\+**, **Génération de code**.  
  
 Une manière plus complète de déterminer les DLL dont dépend votre application consiste à ouvrir celle\-ci à l'aide de Dependency Walker \(depends.exe\).  Vous pouvez télécharger l'outil à partir du site web [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640).  
  
 À l'aide de depends.exe, vous pouvez examiner la liste des DLL qui sont liées à l'application au moment du chargement, ainsi qu'une liste de ses DLL à chargement différé.  Si vous souhaitez obtenir la liste complète des DLL qui sont chargées dynamiquement au moment de l'exécution, vous pouvez utiliser la fonctionnalité de profilage dans depends.exe pour tester l'application jusqu'à ce que vous soyez certain que tous les chemins de code ont été testés.  Une fois la session de profilage terminée, depends.exe indique quelles DLL ont été chargées dynamiquement au moment de l'exécution.  
  
 Lorsque vous utilisez depends.exe, notez qu'une DLL peut être dépendante d'une autre DLL ou d'une version d'une DLL spécifique.  Vous pouvez utiliser depends.exe soit sur l'ordinateur de développement, soit sur un ordinateur cible.  Sur l'ordinateur de développement, depends.exe signale les DLL requises pour prendre en charge une application.  Si vous rencontrez des problèmes pour exécuter une application sur un ordinateur cible, vous pouvez copier depends.exe sur celui\-ci, puis ouvrir l'application dans l'outil afin que vous puissiez déterminer quelles DLL obligatoires manquent ou sont incorrectes.  
  
 Lorsque vous disposez de la liste complète des DLL dont dépend votre application, vous pouvez déterminer celles que vous devez redistribuer avec votre application lors du déploiement vers un autre ordinateur.  Dans la plupart des cas, il n'est pas nécessaire de redistribuer les DLL système, mais vous devrez peut\-être redistribuer les DLL des bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  Pour plus d'informations, consultez [Détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md).  
  
## Voir aussi  
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)