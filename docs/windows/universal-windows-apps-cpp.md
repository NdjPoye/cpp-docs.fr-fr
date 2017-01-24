---
title: "Applications de plateforme Windows universelle (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Applications de plateforme Windows universelle (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les applications de plateforme Windows universelle sont basées sur un ensemble de principes de conception qui utilisent des interfaces utilisateur simples centrées sur le contenu, et qui s'ajustent automatiquement aux différentes tailles d'écran sur différents appareils. Vous créez l'interface utilisateur dans le balisage XAML et le code\-behind en C\+\+ natif. Vous pouvez également créer des composants \(DLL\) qui peuvent être utilisés par des applications de plateforme Windows universelle qui sont écrites dans d'autres langages. La surface de l’API pour les applications de plateforme Windows universelle est le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], qui est une bibliothèque bien factorisée fournissant une grande variété de services de système d’exploitation.  
  
> [!NOTE]
>  L’essentiel de la documentation pour le développement d’applications de plateforme Windows universelle en C\+\+ se trouve sur le site web du [Centre de développement Windows](http://go.microsoft.com/fwlink/p/?LinkId=255563). Certains des liens de cet article vous permettent d’accéder à ce site web.  
  
## Applications de plateforme Windows universelle utilisant C\+\+\/CX  
  
|||  
|-|-|  
|[Informations de référence du langage Visual C\+\+ \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=255561)|Décrit l’ensemble des extensions qui simplifient la consommation par C\+\+ des API de [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et qui activent la gestion des erreurs basée sur les exceptions.|  
|[Génération d’applications et de bibliothèques \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=264858)|Décrit comment créer des DLL et des bibliothèques statiques qui sont accessibles à partir d’une application ou d’un composant C\+\+\/CX.|  
|[Didacticiel : Créer votre première application du Windows Store en C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255556)|Une procédure pas à pas qui présente les concepts de base du développement d’applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] en C\+\+. \(Pas encore mise à jour pour le développement d’applications de plateforme Windows universelle sur Windows 10.\)|  
|[Feuille de route pour les applications du Windows Store en C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255553)|Fournit des liens vers des articles sur le développement d’applications et de jeux du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] en C\+\+.|  
|[Création de composants Windows Runtime en C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=255559)|Décrit comment créer des DLL que d’autres applications et composants du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] peuvent consommer.|  
|[Développement de jeux](http://go.microsoft.com/fwlink/p/?LinkId=255554)|Décrit comment utiliser DirectX et C\+\+ pour créer des jeux.|  
  
## Applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] utilisant la [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\)  
 La bibliothèque [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] fournit les interfaces COM de bas niveau par lesquelles le code C\+\+ ISO peut accéder à [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] dans un environnement sans exception. Dans la plupart des cas, nous vous recommandons d’utiliser C\+\+\/CX au lieu de la bibliothèque [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]pour le développement d’applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]. Pour plus d’informations sur le [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)], consultez [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
## Voir aussi  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)