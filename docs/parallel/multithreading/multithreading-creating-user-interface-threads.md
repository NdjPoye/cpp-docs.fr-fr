---
title: "Multithreading&#160;: cr&#233;ation de threads d&#39;interface utilisateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
  - "SECURITY_ATTRIBUTES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multithreading (C++), threads de l'interface utilisateur"
  - "threads (C++), créer des threads"
  - "threads (C++), threads de l'interface utilisateur"
  - "threads (MFC), threads de l'interface utilisateur"
  - "threads de l'interface utilisateur (C++)"
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading&#160;: cr&#233;ation de threads d&#39;interface utilisateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un thread d'interface utilisateur est généralement utilisé pour gérer les informations entrées par l'utilisateur et répondre aux événements indépendamment des threads exécutant d'autres parties de l'application.  Le principal thread de l'application \(fourni dans votre classe dérivée de `CWinApp`\) est déjà créé et lancé pour vous.  Cette rubrique décrit les étapes nécessaires pour créer des threads d'interface utilisateur supplémentaires.  
  
 La première chose à faire lorsque vous créez un thread d'interface utilisateur est de dériver une classe de [CWinThread](../../mfc/reference/cwinthread-class.md).  Vous devez déclarer et implémenter cette classe à l'aide des macros [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) et [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md).  Cette classe doit substituer certaines fonctions, et peut en substituer d'autres.  Ces fonctions et leur finalité sont présentées dans le tableau suivant.  
  
### Fonctions à substituer lors de la création d'un thread d'interface utilisateur  
  
|Fonction|Objectif|  
|--------------|--------------|  
|[ExitInstance](../Topic/CWinThread::ExitInstance.md)|Procède au nettoyage lorsque le thread arrive au bout de son chemin d'exécution.  Cette fonction est généralement substituée.|  
|[InitInstance](../Topic/CWinThread::InitInstance.md)|Procède à l'initialisation de l'instance du thread.  Cette fonction doit être substituée.|  
|[OnIdle](../Topic/CWinThread::OnIdle.md)|Effectue un traitement quand le thread est au repos.  Cette fonction n'est généralement pas substituée.|  
|[PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|Filtre les messages avant leur distribution à **TranslateMessage** et à **DispatchMessage**.  Cette fonction n'est généralement pas substituée.|  
|[ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|Intercepte les exceptions non reconnues par les gestionnaires de commandes et de messages du thread.  Cette fonction n'est généralement pas substituée.|  
|[Run](../Topic/CWinThread::Run.md)|Fonction de contrôle du thread.  Contient la pompe de messages.  Cette fonction est rarement substituée.|  
  
 MFC fournit deux versions surchargées d'`AfxBeginThread` : à l'aide de la surcharge de paramètre: l'une qui peut seulement créer des threads de travail et l'autre qui peut créer des threads d'interface utilisateur et des threads de travail.  Pour commencer votre thread d'interface utilisateur, appelez la seconde surcharge de [AfxBeginThread](../Topic/AfxBeginThread.md), en fournissant les informations suivantes :  
  
-   La [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md) de la classe que vous avez dérivée de `CWinThread`.  
  
-   \(Facultatif\) Le niveau de priorité voulu.  La priorité normale correspond à la valeur par défaut.  Pour plus d'informations sur les niveaux de priorité disponibles, consultez [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) dans le [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
-   \(Facultatif\) La taille de la pile du thread.  La valeur par défaut est la même taille de pile que celle du thread parent.  
  
-   \(Facultatif\) **CREATE\_SUSPENDED** si vous souhaitez que le thread soit créé dans un état suspendu.  La valeur par défaut est 0, ou démarrez le thread normalement.  
  
-   \(Facultatif\) Les attributs de sécurité souhaités.  La valeur par défaut est le même accès que le thread parent.  Pour plus d'informations sur le format de ces données de sécurité, consultez [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) dans le [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 `AfxBeginThread` accomplit l'essentiel du travail à votre place.  Elle crée un objet de votre classe, l'initialise avec les informations que vous fournissez et appelle [CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md) pour lancer l'exécution du thread.  Des vérifications sont effectuées tout au long de la procédure pour s'assurer que tous les objets sont libérés correctement au cas où une partie de la création échouerait.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Multithreading : arrêt d'exécution des threads](../../parallel/multithreading-terminating-threads.md)  
  
-   [Multithreading : création de threads de travail](../../parallel/multithreading-creating-worker-threads.md)  
  
-   [\<caps:sentence id\="tgt49" sentenceid\="d446961ca833a037f83b141ec4859428" class\="tgtSentence"\>Threads et processus\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## Voir aussi  
 [Multithreading à l'aide de C\+\+ et de MFC](../../parallel/multithreading-with-cpp-and-mfc.md)