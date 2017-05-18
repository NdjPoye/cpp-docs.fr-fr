---
title: "Plateformes prises en charge (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 0192e9bd6ef9d93e274c43c24137a27e5aa53dab
ms.openlocfilehash: c0c209c16ad4a264b851321a2879104112da81f2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="supported-platforms-visual-c"></a>Plateformes prises en charge (Visual C++)
Les applications générées à l'aide de [!INCLUDE[vsprvs](assembler/masm/includes/vsprvs_md.md)] peuvent être ciblées pour différentes plateformes, comme suit.  
  
|Système d'exploitation|x86|x64|ARM|  
|----------------------|---------|---------|---------|  
|Windows XP|X*|X*||  
|[!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)]|X*|X*||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android **|X|X|X|  
|iOS **|X|X|x|  
  
 \* Vous pouvez utiliser l’ensemble d’outils de plateforme Windows XP fourni avec Visual Studio 2015, Visual Studio 2013 et Visual Studio 2012 Update 1 ou version ultérieure pour générer des projets Windows XP et [!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)]. Pour plus d’informations sur la façon d’utiliser cet ensemble d’outils de plateforme, consultez [Configuration des programmes pour Windows XP](build/configuring-programs-for-windows-xp.md). Pour plus d’informations sur la modification de l’ensemble d’outils de plateforme, consultez [Guide pratique pour modifier le framework cible et l’ensemble d’outils de la plateforme](build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
 ** Vous pouvez installer le composant facultatif Visual C++ pour le développement mobile multiplateforme dans le programme d'installation de Visual Studio 2015 pour cibler les plateformes iOS ou Android. Pour obtenir des instructions, consultez [Installer Visual C++ pour le développement mobile multiplateforme](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). Pour générer du code iOS, vous devez disposer d’un ordinateur Mac et satisfaire à d’autres exigences. Pour obtenir une liste des prérequis et des instructions détaillées, consultez [Installer et configurer les outils de génération pour iOS](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Vous pouvez générer du code x86 ou ARM en fonction du matériel cible. Utilisez des configurations x86 pour générer pour le simulateur iOS, pour l'émulateur Microsoft Visual Studio pour Android et pour certains appareils Android. Utilisez des configurations ARM pour générer des applications pour les appareils iOS et la plupart des appareils Android.  
  
 Pour plus d’informations sur la manière de définir la configuration de la plateforme cible, consultez [Guide pratique pour configurer des projets Visual C++ afin de cibler des plateformes 64 bits](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Outils et fonctionnalités Visual C++ dans les éditions de Visual Studio](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)   
 [Prise en main](/visualstudio/ide/getting-started-with-visual-cpp-in-visual-studio)
