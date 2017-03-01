---
title: "Configurations du projet ATL par défaut | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, default configurations
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 41ab65c411bef478d063e5165d3167f58ace37d7
ms.lasthandoff: 02/24/2017

---
# <a name="default-atl-project-configurations"></a>Configurations des projets ATL par défaut
Cette rubrique compare les configurations des projets ATL par défaut dans Visual C++ .NET avec les configurations de projet par défaut dans Visual C++ 6.0.  
  
## <a name="visual-c-net-default-configurations"></a>Configurations par défaut de Visual C++ .NET  
 Dans Visual C++ .NET, l’Assistant Projet ATL crée deux configurations de projet par défaut.  
  
### <a name="visual-c-net-configurations"></a>Configurations Visual C++ .NET  
  
|Configuration|Jeu de caractères|Utilisation des ATL|  
|-------------------|-------------------|----------------|  
|Version finale|MBCS|DLL|  
|Débogage|MBCS|DLL|  
  
 **Jeu de caractères**, **utilisation des ATL** et peut être modifié dans le **paramètres du projet** boîte de dialogue sous la **général** onglet. Vous pouvez également ajouter vos propres configurations à l’aide du Gestionnaire de Configuration. Pour plus d’informations, consultez [des Configurations de Build](/visualstudio/ide/understanding-build-configurations).  
  
## <a name="version-60-default-configurations"></a>Configurations par défaut de la version 6.0  
 Dans la version 6.0 de Visual C++, ATL COM AppWizard (maintenant appelé l’Assistant Projet ATL) créé six configurations de projet par défaut. Les configurations étaient des variations de version, débogage, Unicode et utilisation des paramètres CRT et ATL. Toutes ces configurations peuvent être dupliquées dans Visual C++ .NET à l’aide du Gestionnaire de Configuration, si vous le souhaitez.  
  
### <a name="version-60-configurations"></a>Configurations de la version 6.0  
  
|Configuration|Jeu de caractères|Utilisation des ATL|  
|-------------------|-------------------|----------------|  
|Débogage|MBCS|Statique|  
|Débogage d’Unicode|UNICODE|Statique|  
|Dépendance de version minimale|MBCS|Statique|  
|La version Unicode de dépendance Min|UNICODE|Statique|  
|Version minimum|MBCS|DLL|  
|La version Unicode de taille Min|UNICODE|DLL|  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation avec ATL et le Code C Run-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md)   
 [Boîte de dialogue Gestionnaire de configuration](http://msdn.microsoft.com/en-us/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Compilation et génération](/visualstudio/ide/compiling-and-building-in-visual-studio)


