---
title: "Multithreading&#160;: quand utiliser les classes de synchronisation | Microsoft Docs"
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
  - "accès aux ressources contrôlé (C++)"
  - "multithreading (C++), classes de synchronisation"
  - "ressources (C++), multithreading"
  - "synchronisation (C++), multithreading"
  - "classes d'accès de synchronisation (C++)"
  - "classes de synchronisation (C++)"
  - "threads (C++), synchronisation"
  - "threads (MFC), classes de synchronisation"
ms.assetid: 4914f54e-68ac-438f-93c9-c013455a657e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading&#160;: quand utiliser les classes de synchronisation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes multithread fournies avec MFC se répartissent en deux catégories : les objets de synchronisation \([CSyncObject](../../mfc/reference/csyncobject-class.md), [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md) et [CEvent](../../mfc/reference/cevent-class.md)\) et les objets d'accès de synchronisation \([CMultiLock](../../mfc/reference/cmultilock-class.md) et [CSingleLock](../../mfc/reference/csinglelock-class.md)\).  
  
 Les classes de synchronisation sont utilisées quand l'accès à une ressource doit être contrôlé pour assurer l'intégrité de la ressource.  Les classes d'accès de synchronisation permettent d'obtenir l'accès à ces ressources contrôlées.  Cette rubrique indique quand utiliser chaque classe.  
  
 Pour déterminer la classe de synchronisation à utiliser, posez\-vous les questions suivantes :  
  
1.  Faut\-il que l'application attende qu'un événement se produise avant d'accéder à la ressource \(par exemple, il faut d'abord recevoir les données d'un port de communication avant de pouvoir les écrire dans un fichier\) ?  
  
     Si oui, utilisez `CEvent`.  
  
2.  Au sein d'une application, plusieurs threads peuvent\-ils accéder à cette ressource en même temps \(par exemple, votre application autorise jusqu'à cinq fenêtres avec des vues sur le même document \) ?  
  
     Si oui, utilisez `CSemaphore`.  
  
3.  Cette ressource peut\-elle être utilisée par plusieurs applications \(par exemple, la ressource se trouve dans une DLL\) ?  
  
     Si oui, utilisez `CMutex`.  
  
     Sinon, utilisez `CCriticalSection`.  
  
 **CSyncObject** n'est jamais utilisée directement.  C'est la classe de base des quatre autres classes de synchronisation.  
  
## Exemple 1 : utilisation de trois classes de synchronisation  
 À titre d'exemple, choisissez une application qui gère une liste liée de comptes.  Cette application permet d'examiner jusqu'à trois comptes dans des fenêtres séparées, mais une seule peut être mise à jour à la fois.  Lorsqu'un compte est mis à jour, les données mises à jour sont envoyées via le réseau à une archive de données.  
  
 Cet exemple d'application utilise les trois types de classes de synchronisation.  Dans la mesure où elle permet d'examiner jusqu'à trois comptes à la fois, elle utilise `CSemaphore` pour limiter l'accès à trois objets de vue.  En cas de tentative d'affichage d'un quatrième compte, l'application attend que l'une des trois premières fenêtres se ferme ou elle échoue.  Lorsqu'un compte est mis à jour, l'application utilise `CCriticalSection`pour s'assurer qu'un seul compte est mis à jour à la fois.  Une fois la mise à jour effectuée, elle prévient `CEvent`, qui libère un thread qui attend que l'événement soit signalé.  Ce thread envoie les nouvelles données à l'archive de données.  
  
## Exemple 2 : utilisation des classes d'accès de synchronisation  
 Il est encore plus simple de choisir la classe d'accès de synchronisation à utiliser.  Si votre application est concernée par l'accès à une seule ressource contrôlée, utilisez `CSingleLock`.  Si elle a besoin d'accéder à une ressource contrôlée parmi plusieurs, utilisez `CMultiLock`.  Dans l'exemple 1, `CSingleLock` aurait été utilisée car dans chaque cas où une seule ressource était nécessaire à un moment donné.  
  
 Pour plus d'informations sur l'utilisation des classes de synchronisation, consultez [Multithreading : comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  Pour plus d'informations sur la synchronisation, consultez [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353) dans le [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  Pour plus d'informations sur la prise en charge du multithreading dans MFC, consultez [Multithreading à l'aide de C\+\+ et de MFC](../../parallel/multithreading-with-cpp-and-mfc.md).  
  
## Voir aussi  
 [Multithreading à l'aide de C\+\+ et de MFC](../../parallel/multithreading-with-cpp-and-mfc.md)