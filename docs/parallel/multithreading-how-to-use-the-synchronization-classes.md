---
title: "Multithreading&#160;: comment utiliser les classes de synchronisation | Microsoft Docs"
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
  - "MFC (C++), multithreading"
  - "multithreading (C++), classes de synchronisation"
  - "ressources (C++), multithreading"
  - "synchronisation (C++), multithreading"
  - "classes de synchronisation (C++)"
  - "threads (C++), synchronisation"
  - "threads (C++), conception d'une classe à thread sécurisée"
  - "threads (MFC), classes de synchronisation"
  - "threads (MFC), conception d'une classe à thread sécurisée"
  - "classes à thread sécurisées (C++)"
ms.assetid: f266d4c6-0454-4bda-9758-26157ef74cc5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading&#160;: comment utiliser les classes de synchronisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La synchronisation de l'accès aux ressources entre les threads est un problème fréquent dans l'écriture d'applications multithread.  Le fait d'avoir deux ou plusieurs threads qui accèdent simultanément aux mêmes données peut conduire à des résultats indésirables et imprévisibles.  Par exemple, un thread pourrait mettre à jour le contenu d'une structure pendant qu'un autre thread lirait le contenu de la même structure.  Il n'est pas possible de connaître les données que le thread de lecture recevrait : les données anciennes, les données nouvellement écrites ou un possible mélange des deux.  MFC fournit un certain nombre de classes de synchronisation et de classes d'accès de synchronisation pour faciliter la résolution de ce problème.  Cette rubrique décrit les classes disponibles et explique comment les utiliser pour créer des classes thread\-safe dans une application multithread standard.  
  
 Une application multithread standard possède une classe qui représente une ressource à partager entre les threads.  Avec une classe correctement conçue et complètement thread\-safe, il n'est pas nécessaire d'appeler des fonctions de synchronisation.  Tout est géré de façon interne dans la classe, ce qui vous permet de vous concentrer sur le meilleur moyen d'utiliser la classe, au lieu d'essayer de déterminer si elle risque d'être altérée.  Une technique performante pour créer une classe complètement thread\-safe consiste à fusionner la classe de synchronisation dans la classe de ressource.  La fusion des classes de synchronisation dans la classe partagée est un processus simple.  
  
 À titre d'exemple, choisissez une application qui gère une liste liée de comptes.  Cette application permet d'examiner jusqu'à trois comptes dans des fenêtres séparées, mais une seule peut être mise à jour à la fois.  Lorsqu'un compte est mis à jour, les données mises à jour sont envoyées via le réseau à une archive de données.  
  
 Cet exemple d'application utilise les trois types de classes de synchronisation.  Dans la mesure où elle permet d'examiner jusqu'à trois comptes à la fois, elle utilise [CSemaphore](../mfc/reference/csemaphore-class.md) pour limiter l'accès à trois objets de vue.  En cas de tentative d'affichage d'un quatrième compte, l'application attend que l'une des trois premières fenêtres se ferme ou elle échoue.  Lorsqu'un compte est mis à jour, l'application utilise [CCriticalSection](../mfc/reference/ccriticalsection-class.md) pour s'assurer qu'un seul compte est mis à jour à la fois.  Une fois la mise à jour effectuée, elle prévient [CEvent](../mfc/reference/cevent-class.md), qui libère un thread qui attendait que l'événement soit signalé.  Ce thread envoie les nouvelles données à l'archive de données.  
  
##  <a name="_mfc_designing_a_thread.2d.safe_class"></a> Conception d'une classe thread\-safe  
 Pour créer une classe complètement thread\-safe, ajoutez d'abord la classe de synchronisation appropriée aux classes partagées en tant que membre de données.  Dans le précédent exemple de gestion de comptes, un membre de données **CSemaphore** serait ajouté à la classe de vue, un membre de données `CCriticalSection`serait ajouté à la classe de liste liée et un membre de données `CEvent`serait ajouté à la classe de stockage des données.  
  
 Ensuite, ajoutez des appels de synchronisation à toutes les fonctions membres qui modifient les données dans la classe ou accédez à une ressource contrôlée.  Dans chaque fonction, vous devez créer un objet [CSingleLock](../mfc/reference/csinglelock-class.md) ou [CMultiLock](../mfc/reference/cmultilock-class.md) et appeler la fonction `Lock` de cet objet.  Quand l'objet de verrouillage devient hors de portée et est détruit, le destructeur de l'objet appelle `Unlock` à votre place, libérant ainsi la ressource.  Naturellement, vous pouvez appeler `Unlock` directement, si vous le souhaitez.  
  
 La conception d'une classe thread\-safe de cette façon permet de l'utiliser dans une application multithread aussi facilement qu'une classe non thread\-safe, mais sans risque.  L'encapsulation de l'objet de synchronisation et de l'objet d'accès de synchronisation dans la classe de la ressource offre tous les avantages d'une programmation complètement thread\-safe sans l'inconvénient de gestion d'un code de synchronisation.  
  
 L'exemple de code suivant illustre cette méthode en utilisant un membre de données, `m_CritSection` \(de type `CCriticalSection`\), déclaré dans la classe de ressources partagées et un objet `CSingleLock`.  Une tentative de synchronisation de la ressource partagée \(dérivée de `CWinThread`\) est amorcée par la création d'un objet `CSingleLock` à l'aide de l'adresse de l'objet `m_CritSection`.  Une tentative est effectuée pour verrouiller la ressource et, une fois cette tâche accomplie, le travail porte sur l'objet partagé.  Une fois le travail terminé, la ressource est déverrouillée à l'aide d'un appel à `Unlock`.  
  
```  
CSingleLock singleLock(&m_CritSection);  
singleLock.Lock();  
// resource locked  
//.usage of shared resource...  
  
singleLock.Unlock();  
```  
  
> [!NOTE]
>  Contrairement aux classes de synchronisation MFC, `CCriticalSection` n'offre pas l'option d'une demande de verrouillage temporisée.  Le délai d'attente de la libération d'un thread est illimité.  
  
 Cette approche a pour inconvénient que la classe est légèrement plus lente que la même classe sans les objets de synchronisation ajoutés.  Par ailleurs, si plusieurs threads risquent de supprimer l'objet, l'approche de fusion ne fonctionne pas toujours.  Dans cette situation, il vaut mieux maintenir des objets de synchronisation séparés.  
  
 Pour plus d'informations sur la manière de déterminer les classes de synchronisation à utiliser dans les différentes situations, consultez [Multithreading : quand utiliser les classes de synchronisation](../parallel/multithreading-when-to-use-the-synchronization-classes.md).  Pour plus d'informations sur la synchronisation, consultez [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  Pour plus d'informations sur la prise en charge du multithreading dans MFC, consultez [Multithreading à l'aide de C\+\+ et de MFC](../parallel/multithreading-with-cpp-and-mfc.md).  
  
## Voir aussi  
 [Multithreading à l'aide de C\+\+ et de MFC](../parallel/multithreading-with-cpp-and-mfc.md)