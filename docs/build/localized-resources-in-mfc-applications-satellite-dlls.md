---
title: "Ressources localis&#233;es dans des applications MFC&#160;: DLL satellites | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), localiser des MFC"
  - "localisation (C++), ressources MFC"
  - "ressources localisées (C++)"
  - "DLL MFC (C++), localiser"
  - "prise en charge multilingue (C++)"
  - "DLL de ressources uniquement (C++)"
  - "DLL de ressources uniquement (C++), applications MFC"
  - "ressources (MFC), localiser"
  - "DLL satellites (C++)"
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ressources localis&#233;es dans des applications MFC&#160;: DLL satellites
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC version 7.0 et les versions ultérieures fournissent une prise en charge améliorée pour les DLL satellites, une fonctionnalité qui vous aide à créer des applications localisées pour différentes langues.  Une DLL satellite est une [DLL de ressource uniquement](../build/creating-a-resource-only-dll.md) qui contient les ressources localisées d'une application pour une langue particulière.  Lorsque l'application commence à s'exécuter, MFC charge automatiquement la ressource localisée la plus appropriée pour l'environnement.  Par exemple, vous pouvez avoir une application pourvue de ressources pour la langue anglaise avec deux DLL satellites : la première contenant la version française des ressources et la deuxième la version allemande.  Lorsque l'application est exécutée sur un système en anglais, celui\-ci utilise les ressources de la langue anglaise.  Si l'application est exécutée sur un système en français, les ressources du français sont utilisées ; si elle est exécutée sur un système en allemand, ce sont les ressources de l'allemand qui sont utilisées.  
  
 Pour prendre en charge des ressources localisées dans une application MFC, MFC tente de charger une DLL satellite contenant les ressources localisées d'une langue spécifique.  Les DLL satellites sont nommées *NomApplicationXXX*.dll, où *NomApplication* est le nom du fichier .exe ou .dll utilisant MFC, et *XXX* le code de trois lettres correspondant à la langue des ressources \(par exemple, « ENU » ou « DEU »\).  
  
 MFC essaie de charger la DLL de ressource pour chacune des langues suivantes dans l'ordre, en s'arrêtant quand elle en trouve une :  
  
1.  \(Windows 2000 ou version ultérieure seulement\) La langue de l'interface utilisateur par défaut de l'utilisateur en cours retournée par l'API Win32 GetUserDefaultUILanguage\(\).  
  
2.  \(Windows 2000 ou version ultérieure uniquement\) la langue de l'interface utilisateur par défaut de l'utilisateur actuel, sans sous\-langue spécifique \(par exemple, ENC \[anglais du Canada\] devient ENU \[anglais  des États\-Unis\]\).  
  
3.  La langue de l'interface utilisateur par défaut du système.  Sur Windows 2000 ou version ultérieure, cette valeur est retournée par l'API GetSystemDefaultUILanguage\(\).  Sur d'autres plateformes, il s'agit de la langue du système d'exploitation lui\-même.  
  
4.  La langue de l'interface utilisateur par défaut du système, sans aucune sous\-langue spécifique.  
  
5.  Une langue factice avec le code à 3 lettres LOC.  
  
 Si MFC ne trouve aucune DLL satellite, elle utilise les ressources contenues dans l'application même.  
  
 Par exemple, supposez qu'une application LangExample.exe utilise MFC et fonctionne sur un système à plusieurs interfaces utilisateur Windows 2000 ; la langue de l'interface utilisateur du système est ENU \[anglais des États\-Unis\]  et la langue de l'interface utilisateur de l'utilisateur actuel a la valeur FRC \[français canadien\].  MFC recherche les DLL suivantes, dans l'ordre :  
  
1.  LangExampleFRC.dll \(langue de l'interface utilisateur de l'utilisateur en cours\).  
  
2.  LangExampleFRA.dll \(langue de l'interface utilisateur sans sous\-langue, dans cet exemple Français \(France\).  
  
3.  LangExampleENU.dll \(langue de l'interface utilisateur du système\).  
  
4.  LangExampleLOC.dll.  
  
 Si aucune de ces DLL n'est trouvée, MFC utilise alors les ressources contenues dans LangExample.exe.  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [TN057 : localisation des composants MFC](../mfc/tn057-localization-of-mfc-components.md)