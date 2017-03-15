---
title: "Plateformes prises en charge (Visual&#160;C++) | Microsoft Docs"
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
  - "plateformes (C++)"
  - "Visual C++, plateformes prises en charge"
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Plateformes prises en charge (Visual&#160;C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les applications générées à l'aide de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] peuvent être ciblées pour différentes plateformes, comme suit.  
  
|Système d'exploitation|x86|x64|ARM|  
|----------------------------|---------|---------|---------|  
|Windows XP|X\*|X\*||  
|[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|X\*|X\*||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android \*\*|X|X|X|  
|iOS \*\*|X|X|X|  
  
 \* Vous pouvez utiliser l'ensemble d'outils de plateforme Windows XP fourni avec Visual Studio 2015, Visual Studio 2013 et Visual Studio 2012 Update 1 ou version ultérieure pour générer des projets Windows XP et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Pour plus d'informations sur la façon d'utiliser cet ensemble d'outils de plateforme, consultez [Configuration des programmes C\+\+ 11 pour Windows XP](../build/configuring-programs-for-windows-xp.md).  Pour plus d'informations sur la modification de l'ensemble d'outils de plateforme, consultez [comment : modifier la version cible de .Net Framework et l'ensemble d'outils de la plateforme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
 \*\* Vous pouvez installer le composant facultatif Visual C\+\+ pour le développement mobile multiplateforme dans le programme d'installation de Visual Studio 2015 pour cibler les plateformes iOS ou Android.  Pour obtenir des instructions, consultez [Installer Visual C\+\+ pour le développement mobile multiplateforme](../Topic/Install%20Visual%20C++%20for%20Cross-Platform%20Mobile%20Development.md).  Pour générer du code iOS, vous devez disposer d'un ordinateur Mac et satisfaire à d'autres exigences.  Pour obtenir une liste des conditions préalables et des instructions détaillées, consultez [Installer et configurer des outils de génération en utilisant iOS](../Topic/Install%20And%20Configure%20Tools%20to%20Build%20using%20iOS.md).  Vous pouvez générer du code x86 ou ARM en fonction du matériel cible.  Utilisez des configurations x86 pour générer pour le simulateur iOS, pour l'émulateur Microsoft Visual Studio pour Android et pour certains appareils Android.  Utilisez des configurations ARM pour générer des applications pour les appareils iOS et la plupart des appareils Android.  
  
 Pour plus d'informations sur la manière de définir la configuration de la plateforme cible, consultez [Comment : configurer des projets Visual C\+\+ pour cibler des plateformes 64 bits](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
## Voir aussi  
 [Outils et modèles Visual C\+\+ dans les éditions Visual Studio](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)   
 [Prise en main](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md)