---
title: "Proc&#233;dure pas &#224; pas&#160;: suppression de travail d&#39;un thread d&#39;interface utilisateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "supprimer du travail de threads d'interface utilisateur (runtime d'accès concurrentiel)"
  - "threads d'interface utilisateur, supprimer du travail de (runtime d'accès concurrentiel)"
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
caps.latest.revision: 14
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: suppression de travail d&#39;un thread d&#39;interface utilisateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce document montre comment utiliser le runtime d'accès concurrentiel pour déplacer le travail exécuté par le thread d'interface utilisateur dans une application Microsoft Foundation Classes \(MFC\) vers un thread de travail.  Ce document montre également comment améliorer les performances d'une longue opération de dessin.  
  
 En déplaçant un travail du thread d'interface utilisateur par le déchargement des opérations bloquantes, telles que le dessin, vers des threads de travail peut améliorer la réactivité de votre application.  Cette procédure pas à pas utilise une routine de dessin qui génère une fractale de Mandelbrot pour démontrer une longue opération bloquante.  La génération de fractales de Mandelbrot est aussi une candidate idéale pour la parallélisation car le calcul de chaque pixel est indépendant de tous les autres calculs.  
  
## Composants requis  
 Lisez les rubriques suivantes avant de démarrer cette procédure pas\-à\-pas :  
  
-   [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)  
  
-   [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)  
  
-   [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md)  
  
 Nous vous recommandons également de connaître les bases du développement d'applications MFC et de [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] avant de démarrer cette procédure pas à pas.  Pour plus d'informations concernant MFC, consultez [MFC, applications de bureau](../../mfc/mfc-desktop-applications.md).  Pour plus d'informations sur [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)], consultez [GDI\+](_gdiplus_GDI_start_cpp).  
  
##  <a name="top"></a> Sections  
 Cette procédure pas\-à\-pas contient les sections suivantes :  
  
-   [Création d'une application MFC](#application)  
  
-   [Implémentation de la version sérialisée de l'application Mandelbrot](#serial)  
  
-   [Suppression d'un travail du thread d'interface utilisateur](#removing-work)  
  
-   [Amélioration des performances de dessin](#performance)  
  
-   [Ajout de prise en charge pour l'annulation](#cancellation)  
  
##  <a name="application"></a> Création d'une application MFC  
 Cette section décrit comment créer une application MFC de base.  
  
### Pour créer une application MFC en Visual C\+\+  
  
1.  Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet**.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, sélectionnez **Visual C\+\+** dans le volet , puis cliquez sur **Application MFC** dans le volet **Modèles**.  Tapez un nom pour le projet, par exemple `Mandelbrot`, puis cliquez sur **OK** pour afficher l'**Assistant Application MFC**.  
  
3.  Dans le volet **Type d'application**, sélectionnez **Document unique**.  Assurez\-vous que la case à cocher **Prise en charge de l'architecture Document\/Vue** est désactivée.  
  
4.  Cliquez sur **Terminer** pour créer le projet et fermer l'**Assistant Application MFC**.  
  
     Vérifiez que l'application a été créée avec succès en la générant et en l'exécutant.  Pour générer l'application, dans le menu **Générer**, cliquez sur **Générer la solution**.  Si l'application est générée avec succès, exécutez\-la en cliquant sur le bouton **Démarrer le débogage** dans le menu **Déboguer**.  
  
##  <a name="serial"></a> Implémentation de la version sérialisée de l'application Mandelbrot  
 Cette section décrit comment dessiner une fractale de Mandelbrot.  Cette version dessine la fractale de Mandelbrot dans un objet [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)][Bitmap](https://msdn.microsoft.com/en-us/library/ms534420.aspx) puis copie le contenu de cet objet bitmap dans la fenêtre cliente.  
  
#### Pour implémenter la version sérialisée de l'application Mandelbrot  
  
1.  Dans stdafx.h, ajoutez la directive `#include` suivante :  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  Dans ChildView.h, après la directive `pragma`, définissez le type `BitmapPtr`.  Le type `BitmapPtr` permet au pointeur d'un objet `Bitmap` d'être partagé par plusieurs composants.  L'objet `Bitmap` est supprimé lorsqu'il n'est référencé par aucun composant.  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  Dans ChildView.h, ajoutez le code suivant à la section `protected` de la classe `CChildView` :  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  Dans ChildView.cpp, supprimez ou commentez les lignes suivantes.  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     Dans les versions Debug, cette étape empêche l'application d'utiliser l'allocateur `DEBUG_NEW`, qui est incompatible avec [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
5.  Dans ChildView.cpp, ajoutez une directive `using` à l'espace de noms `Gdiplus`.  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  Ajoutez le code suivant au constructeur et destructeur de la classe `CChildView` pour initialiser et arrêter [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)].  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  Implémentez la méthode `CChildView::DrawMandelbrot`.  Cette méthode dessine la fractale de Mandelbrot dans l'objet `Bitmap` spécifié.  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  Implémentez la méthode `CChildView::OnPaint`.  Cette méthode appelle `CChildView::DrawMandelbrot` puis copie le contenu de l'objet `Bitmap` vers la fenêtre.  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. Vérifiez que l'application a été mise à jour avec succès en la générant et en l'exécutant.  
  
 L'illustration suivante présente les résultats de l'application Mandelbrot.  
  
 ![L'application Mandelbrot](../../parallel/concrt/media/mandelbrot.png "Mandelbrot")  
  
 Étant donné que le calcul de chaque pixel est gourmand en ressources informatiques, le thread d'interface utilisateur ne peut pas traiter de messages supplémentaires avant la fin du calcul final.  Cela peut diminuer la réactivité dans l'application.  Toutefois, il est possible d'atténuer ce problème en supprimant du travail d'un thread d'interface utilisateur.  
  
 \[[Premières](#top)\]  
  
##  <a name="removing-work"></a> Suppression de travail d'un thread d'interface utilisateur  
 Cette section indique comment supprimer du travail de dessin d'un thread d'interface utilisateur dans l'application Mandelbrot.  En déplaçant du travail de dessin d'un thread d'interface utilisateur vers un thread de travail, vous permettez au thread d'interface utilisateur de traiter des messages pendant que le thread de travail génère l'image en arrière\-plan.  
  
 Le runtime d'accès concurrentiel offre trois moyens d'exécuter des tâches : [groupes de tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [agents asynchrones](../../parallel/concrt/asynchronous-agents.md) et [tâches légères](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  Bien que vous puissiez utiliser n'importe lequel de ces mécanismes pour supprimer du travail d'un thread d'interface utilisateur, cet exemple utilise un objet [concurrency::task\_group](../Topic/task_group%20Class.md) car les groupes de tâches prennent en charge l'annulation.  Cette procédure pas à pas utilise plus tard l'annulation pour réduire la quantité de travail exécutée lorsque la fenêtre cliente est redimensionnée et pour effectuer un nettoyage lorsque la fenêtre est détruite.  
  
 Cet exemple utilise également un objet [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) pour permettre au thread d'interface utilisateur et au thread de travail de communiquer l'un avec l'autre.  Après avoir produit l'image, le thread de travail envoie un pointeur de l'objet `Bitmap` vers l'objet `unbounded_buffer` puis envoie un message de peinture au thread d'interface utilisateur.  Le thread d'interface utilisateur reçoit ensuite de l'objet `unbounded_buffer` l'objet `Bitmap` et le dessine dans la fenêtre cliente.  
  
#### Pour supprimer du travail de dessin d'un thread d'interface utilisateur  
  
1.  Dans stdafx.h, ajoutez les directives `#include` suivantes :  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  Dans ChildView.h, ajoutez des variables membres `task_group` et `unbounded_buffer` à la section `protected` de la classe `CChildView`.  L'objet `task_group` contient les tâches qui exécutent le dessin ; l'objet `unbounded_buffer` contient l'image Mandelbrot terminée.  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  Dans ChildView.cpp, ajoutez une directive `using` à l'espace de noms `concurrency`.  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  
4.  Dans la méthode `CChildView::DrawMandelbrot`, après l'appel à `Bitmap::UnlockBits`, appelez la fonction [concurrency::send](../Topic/send%20Function.md) pour passer l'objet `Bitmap` au thread d'interface utilisateur.  Envoyez ensuite un message de peinture au thread d'interface utilisateur et invalidez la zone client.  
  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  Mettez à jour la méthode `CChildView::OnPaint` pour recevoir l'objet `Bitmap` mis à jour et dessiner l'image dans la fenêtre cliente.  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     La méthode `CChildView::OnPaint` crée une tâche pour générer l'image Mandelbrot si une image n'est pas déjà présente dans le tampon de messages.  Le tampon de messages ne contiendra pas d'objet `Bitmap` pour le message de peinture initial et lorsqu'une autre fenêtre est déplacée devant la fenêtre cliente.  
  
6.  Vérifiez que l'application a été mise à jour avec succès en la générant et en l'exécutant.  
  
 L'interface utilisateur est maintenant plus réactive car le travail de dessin est exécuté en arrière\-plan.  
  
 \[[Premières](#top)\]  
  
##  <a name="performance"></a> Amélioration des performances de dessin  
 La génération de fractales de Mandelbrot est une candidate idéale pour la parallélisation car le calcul de chaque pixel est indépendant de tous les autres calculs.  Pour paralléliser la procédure de dessin, convertissez la boucle `for` externe dans la méthode `CChildView::DrawMandelbrot` en un appel à l'algorithme [concurrency::parallel\_for](../Topic/parallel_for%20Function.md), de la manière suivante.  
  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 Étant donné que le calcul de chaque élément de bitmap est indépendant, vous n'avez pas à synchroniser les opérations de dessin qui accèdent à la mémoire bitmap.  Cela permet aux performances de s'adapter à l'augmentation des processeurs disponibles.  
  
 \[[Premières](#top)\]  
  
##  <a name="cancellation"></a> Ajout de prise en charge pour l'annulation  
 Cette section décrit comment gérer le redimensionnement de fenêtre et comment annuler toutes les tâches de dessin actives lorsque la fenêtre est détruite.  
  
 Le document [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md) explique le fonctionnement de l'annulation dans le runtime.  L'annulation est coopérative, par conséquent, elle ne se produit pas immédiatement.  Pour arrêter une tâche annulée, le runtime lève une exception interne pendant un appel suivant, depuis la tâche dans le runtime.  La section précédente indique comment utiliser l'algorithme `parallel_for` pour améliorer les performances de tâche de dessin.  L'appel à `parallel_for` permet à l'exécution d'arrêter la tâche, et par conséquent, à l'annulation de fonctionner.  
  
### Annulation des tâches actives  
 L'application Mandelbrot crée des objets `Bitmap` dont les dimensions correspondent à la taille de la fenêtre cliente.  Chaque fois que la fenêtre cliente est redimensionnée, l'application crée une tâche supplémentaire en arrière\-plan pour générer une image pour la nouvelle taille de la fenêtre.  L'application ne requiert pas ces images intermédiaires mais uniquement l'image pour la dernière taille de la fenêtre.  Pour empêcher l'application d'exécuter ce travail supplémentaire, vous pouvez annuler toutes les tâches de dessin actives dans les gestionnaires de messages pour les messages `WM_SIZING` et `WM_SIZE` , puis replanifier le travail de dessin une fois la fenêtre redimensionnée.  
  
 Pour annuler des tâches de dessin actives lorsque la fenêtre est redimensionnée, l'application appelle la méthode [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) dans les gestionnaires, pour les messages `WM_SIZE` et `WM_SIZING`.  Le gestionnaire du message `WM_SIZE` appelle également la méthode [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md) pour attendre que toutes les tâches actives soient terminées, puis replanifie la tâche de dessin pour la taille de la fenêtre mise à jour.  
  
 Lorsque la fenêtre cliente est détruite, il s'agit de la méthode conseillée pour annuler toutes les tâches de dessin actives.  L'annulation de toutes les tâches de dessin actives permet de s'assurer que les threads de travail n'envoient pas de messages au thread d'interface utilisateur une fois la fenêtre cliente détruite.  L'application annule toutes les tâches de dessin actives dans le gestionnaire pour le message `WM_DESTROY`.  
  
### Réponse à l'annulation  
 La méthode `CChildView::DrawMandelbrot`, qui exécute la tâche de dessin, doit répondre à l'annulation.  Étant donné que l'exécution utilise la gestion des exceptions pour annuler des tâches, la méthode `CChildView::DrawMandelbrot` doit utiliser un mécanisme sécurisé du point de vue des exceptions pour garantir que toutes les ressources sont correctement nettoyées.  Cet exemple utilise le modèle *RAII \(Resource Acquisition Is Initialization\)* pour garantir que les bits de la bitmap soient déverrouillés lorsque la tâche est annulée.  
  
##### Pour ajouter une prise en charge de l'annulation à l'application Mandelbrot  
  
1.  Dans ChildView.h, dans la section `protected` de la classe `CChildView`, ajoutez des déclarations pour les fonctions de table de messages `OnSize`, `OnSizing` et `OnDestroy`.  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  Dans ChildView.cpp, modifiez la table des messages pour qu'elle contienne des gestionnaires pour les messages `WM_SIZE`, `WM_SIZING` et `WM_DESTROY`.  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  Implémentez la méthode `CChildView::OnSizing`.  Cette méthode annule toutes les tâches de dessin existantes.  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  Implémentez la méthode `CChildView::OnSize`.  Cette méthode annule toutes les tâches de dessin existantes et crée une tâche de dessin pour la taille de la fenêtre cliente mise à jour.  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  Implémentez la méthode `CChildView::OnDestroy`.  Cette méthode annule toutes les tâches de dessin existantes.  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  Dans ChildView.cpp, définissez la classe `scope_guard`, qui implémente le modèle RAII.  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  Ajoutez le code suivant à la méthode `CChildView::DrawMandelbrot` après l'appel à `Bitmap::LockBits`:  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     Ce code gère l'annulation en créant un objet `scope_guard`.  Lorsque l'objet quitte la portée, il déverrouille les bits de la bitmap.  
  
8.  Modifiez la fin de la méthode `CChildView::DrawMandelbrot` pour renvoyer l'objet `scope_guard` une fois les bits de la bitmap déverrouillés, mais avant que tous les messages soient envoyés au thread d'interface utilisateur.  Cela permet de s'assurer que le thread d'interface utilisateur n'est pas mis à jour avant que les bits de la bitmap ne soient déverrouillés.  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. Vérifiez que l'application a été mise à jour avec succès en la générant et en l'exécutant.  
  
 Lorsque vous redimensionnez la fenêtre, le travail de dessin est exécuté uniquement pour la taille finale de la fenêtre.  Toutes les tâches de dessin actives sont également annulées lorsque la fenêtre est détruite.  
  
 \[[Premières](#top)\]  
  
## Voir aussi  
 [Procédures pas à pas relatives au runtime d'accès concurrentiel](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Parallélisme des tâches](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)   
 [Algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md)   
 [Annulation](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [MFC, applications de bureau](../../mfc/mfc-desktop-applications.md)