---
title: "Traitement des boucles inactives | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "traitement en arrière-plan"
  - "traitement des boucles inactives"
  - "traitement des temps d'inactivité"
  - "messages, boucles"
  - "MFC, traitement en arrière-plan"
  - "MFC, messages"
  - "OnIdle (méthode)"
  - "PeekMessage (méthode)"
  - "PeekMessage (méthode), ailleurs que dans la boucle de message"
  - "traiter"
  - "traiter, arrière-plan"
  - "traiter, pendant la boucle inactive"
  - "threads (MFC), alternatives au multithreading"
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement des boucles inactives
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

De nombreuses applications effectuent le traitement lent « en arrière\-plan. » Parfois des performances dictent l'aide du multithreading pour ce travail.  Les threads impliquent la charge mémoire de développement, ils ne sont pas recommandés pour les tâches simples comme le travail avec des temps d'inactivité que MFC fait dans la fonction [OnIdle](../Topic/CWinThread::OnIdle.md).  Cet article se concentre sur le traitement des temps d'inactivité.  Pour plus d'informations sur le multithreading, consultez [Multithreading Topics](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Certains types de traitement en arrière\-plan sont correctement effectués pendant les intervalles où l'utilisateur n'interagit pas avec l'application.  Dans une application développée pour le système d'exploitation Microsoft Windows, une application peut effectuer le traitement en tant les temps d'inactivité en divisant un processus longue à de nombreux petits fragments.  Après avoir traité chaque fragment, l'application réalise la commande d'exécution de Windows en utilisant une boucle [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943).  
  
 Cet article décrit deux méthodes pour effectuer le traitement du temps d'inactivité dans votre application :  
  
-   Utilisation de **PeekMessage** dans la boucle de message principale de MFC.  
  
-   Incorporant d'une autre boucle **PeekMessage** ailleurs dans l'application.  
  
##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a> PeekMessage de la boucle de message de MFC  
 Dans une application développée avec MFC, la boucle de message clé dans la classe `CWinThread` contient une boucle de message qui appelle l'API Win32 [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943).  Cette boucle appelle également la fonction membre `OnIdle` de `CWinThread` entre les messages.  Une application peut traiter les messages dans cette durée d'inactivité en éditant la fonction `OnIdle`.  
  
> [!NOTE]
>  **Exécuter**, `OnIdle`, et certains autres fonctions membres sont désormais des membres de la classe `CWinThread` au lieu de la classe `CWinApp`.  `CWinApp` est dérivé de `CWinThread`.  
  
 Pour plus d'informations sur la manière d'effectuer le traitement du temps d'inactivité, consultez [OnIdle](../Topic/CWinThread::OnIdle.md) dans *le guide de MFC*.  
  
##  <a name="_core_peekmessage_elsewhere_in_your_application"></a> PeekMessage ailleurs dans votre application  
 Une autre méthode pour effectuer le traitement du temps d'inactivité d'une application implique l'incorporation d'une boucle de message dans une de vos fonctions.  Cette boucle de message est très similaire à la boucle de message principale de MFC, trouvé dans [CWinThread::Run](../Topic/CWinThread::Run.md).  Cela signifie que cette boucle dans une application développée avec MFC doit exécuter de nombreuses fonctions que la boucle de message principale.  Le fragment de code suivant montre comment écrire une boucle de message compatible avec MFC :  
  
 [!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/CPP/idle-loop-processing_1.cpp)]  
  
 Ce code, incorporé dans une fonction, une boucle aussi longtemps qu'il restera de temps d'inactivité à effectuer.  Dans cette boucle, une boucle imbriquée est appelée à plusieurs reprises **PeekMessage**.  Comme cet appel retourne une valeur différente de zéro, la boucle appelle `CWinThread::PumpMessage` pour exécuter la traduction et de distribuer standard de message.  Bien que `PumpMessage` soit non documenté, vous pouvez examiner son code source dans le fichier de ThrdCore.Cpp dans le répertoire d'atlmfc\\src\\cpc de l'installation de Visual C\+\+.  
  
 Une fois que la boucle interne se termine, la boucle externe effectue le traitement des temps d'inactivité à un ou plusieurs appels à `OnIdle`.  Le premier appel à MFC.  Vous pouvez effectuer des appels supplémentaires à `OnIdle` pour effectuer votre propre travail en arrière\-plan.  
  
 Pour plus d'informations sur la manière d'effectuer le traitement du temps d'inactivité, consultez [OnIdle](../Topic/CWinThread::OnIdle.md) dans la référence de bibliothèque de MFC.  
  
## Voir aussi  
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)