---
title: "Configurations des projets ATL par d&#233;faut | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, configurations par défaut"
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Configurations des projets ATL par d&#233;faut
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique compare les configurations de projets ATL par défaut de Visual C\+\+ .NET avec celles de Visual C\+\+ 6.0.  
  
## Configurations Visual C\+\+ .NET par défaut  
 Dans Visual C\+\+ .NET, l'Assistant Projet ATL crée deux configurations de projet par défaut.  
  
### Configurations Visual C\+\+ .NET  
  
|Configuration|Jeu de caractères|Utilisation des ATL|  
|-------------------|-----------------------|-------------------------|  
|Release|MBCS|DLL|  
|Débogage|MBCS|DLL|  
  
 Il est possible de modifier les options **Jeu de caractères** et **Utilisation des ATL** dans la boîte de dialogue **Paramètres du projet** sous l'onglet **Général**.  Vous pouvez également ajouter vos propres configurations à l'aide du Gestionnaire de configuration.  Pour plus d'informations, consultez [Configurations de build](../Topic/Understanding%20Build%20Configurations.md).  
  
## Configurations par défaut de la version 6.0  
 Dans Visual C\+\+ .NET version 6.0, l'Assistant Projet ATL \(anciennement ATL COM AppWizard\) a créé six configurations de projet par défaut.  Ces configurations étaient des variations de Version, Débogage, Unicode et de l'utilisation des paramètres CRT et ATL.  Il est possible de les dupliquer dans Visual C\+\+ .NET à l'aide du Gestionnaire de configuration, si besoin est.  
  
### Configurations de la version 6.0  
  
|Configuration|Jeu de caractères|Utilisation des ATL|  
|-------------------|-----------------------|-------------------------|  
|Débogage|MBCS|Static|  
|Débogage d'Unicode|UNICODE|Static|  
|Dépendance minimale de la version|MBCS|Static|  
|Dépendance minimale de la version Unicode|UNICODE|Static|  
|Taille minimale de la version|MBCS|DLL|  
|Taille minimale de la version Unicode|UNICODE|DLL|  
  
## Voir aussi  
 [Programmation avec ATL et le code C Run\-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md)   
 [Configuration Manager Dialog Box](http://msdn.microsoft.com/fr-fr/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Génération d'applications dans Visual Studio](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)