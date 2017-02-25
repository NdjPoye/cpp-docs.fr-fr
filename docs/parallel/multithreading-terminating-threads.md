---
title: "Multithreading&#160;: arr&#234;t d&#39;ex&#233;cution des threads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxEndThread (méthode)"
  - "multithreading (C++), arrêter des threads"
  - "arrêt d'exécution prématuré d'un thread"
  - "démarrer des threads"
  - "interrompre des threads"
  - "arrêter des threads"
  - "threads (C++), interrompre des threads"
  - "threads (MFC), arrêter des threads"
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Multithreading&#160;: arr&#234;t d&#39;ex&#233;cution des threads
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deux situations normales peuvent entraîner l'arrêt d'exécution d'un thread : la fonction de contrôle se ferme ou le thread ne peut pas s'exécuter jusqu'à son achèvement total.  Si un programme de traitement de texte utilise un thread pour l'impression en arrière\-plan, la fonction de contrôle s'arrêtera normalement si l'impression se termine correctement.  Si l'utilisateur souhaite annuler l'impression, le thread d'impression en arrière\-plan doit être arrêté avant terme.  Cette rubrique explique à la fois comment implémenter chaque situation et comment obtenir le code de sortie d'un thread qui se termine.  
  
-   [Arrêt d'exécution normal d'un thread](#_core_normal_thread_termination)  
  
-   [Arrêt d'exécution prématuré d'un thread](#_core_premature_thread_termination)  
  
-   [Récupération du code de sortie d'un thread](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> Arrêt d'exécution normal d'un thread  
 Pour un thread de travail, l'arrêt d'exécution normal est simple : quittez la fonction de contrôle et retournez une valeur qui indique la raison de l'arrêt d'exécution.  Vous pouvez utiliser la fonction [AfxEndThread](../Topic/AfxEndThread.md) ou une instruction `return`.  En principe, 0 signifie l'achèvement correct, mais la décision finale vous revient.  
  
 Pour un thread d'interface utilisateur, le processus est tout aussi simple : dans le thread d'interface utilisateur, appelez [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  Le seul paramètre que **PostQuitMessage** accepte est le code de sortie du thread.  Comme pour les threads de travail, 0 signifie généralement un achèvement correct.  
  
##  <a name="_core_premature_thread_termination"></a> Arrêt d'exécution prématuré d'un thread  
 L'arrêt avant terme d'un thread est presque aussi simple : appelez [AfxEndThread](../Topic/AfxEndThread.md) à partir du thread.  Passez le code de sortie voulu comme paramètre unique.  Ceci arrête l'exécution du thread, libère la pile du thread, déconnecte toutes les DLL connectées au thread et supprime l'objet thread dans la mémoire.  
  
 `AfxEndThread` doit être appelée à partir du thread à arrêter.  Si vous souhaitez arrêter un thread à partir d'un autre thread, vous devez définir un mode de communication entre les deux threads.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> Récupération du code de sortie d'un thread  
 Pour obtenir le code de sortie du thread de travail ou d'interface utilisateur, appelez la fonction [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  Pour plus d'informations sur cette fonction, consultez le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  Cette fonction prend le handle du thread \(stocké dans le membre de données `m_hThread` des objets `CWinThread`\) et l'adresse d'un `DWORD`.  
  
 Si le thread est toujours actif, **GetExitCodeThread** place **STILL\_ACTIVE** dans l'adresse `DWORD` fournie ; autrement, le code de sortie est placé dans cette adresse.  
  
 La récupération du code de sortie des objets [CWinThread](../mfc/reference/cwinthread-class.md) passe par une étape supplémentaire.  Par défaut, quand un thread `CWinThread` se termine, l'objet thread est supprimé.  Cela signifie que vous ne pouvez pas accéder au membre de données `m_hThread` car l'objet `CWinThread` n'existe plus.  Pour éviter cette situation, effectuez l'une des opérations suivantes :  
  
-   Attribuez à la donnée membre `m_bAutoDelete` la valeur **FALSE**.  Cela permet à l'objet `CWinThread` de survivre à l'arrêt d'exécution du thread.  Vous pouvez alors accéder au membre de données `m_hThread` après la terminaison du thread.  Si vous utilisez cette technique, cependant, vous vous chargez de la destruction de l'objet `CWinThread` dans la mesure où la structure ne le supprimera pas automatiquement à votre place.  C'est la méthode conseillée.  
  
-   Stockez le handle du thread séparément.  Une fois le thread créé, copiez son membre de données `m_hThread` \(en utilisant **::DuplicateHandle**\) vers une autre variable et accédez\-y par l'intermédiaire de cette variable.  L'objet est ainsi supprimé automatiquement dès son achèvement et vous pouvez toujours savoir pourquoi le thread s'est arrêté.  Assurez\-vous que le thread ne se termine pas avant que vous n'ayez pu dupliquer le handle.  Le moyen le plus sûr pour accomplir cette tâche est de passer **CREATE\_SUSPENDED** à [AfxBeginThread](../Topic/AfxBeginThread.md), de stocker le handle, puis de reprendre le thread en appelant [ResumeThread](../Topic/CWinThread::ResumeThread.md).  
  
 Les deux méthodes vous permettent de déterminer pourquoi un objet `CWinThread` s'est arrêté.  
  
## Voir aussi  
 [Multithreading à l'aide de C\+\+ et de MFC](../parallel/multithreading-with-cpp-and-mfc.md)   
 [\_endthread, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)