---
title: "CWinThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinThread (classe)"
  - "threads (MFC), créer des threads"
  - "threads (MFC), sécurité"
  - "threads de travail"
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un thread d'exécution dans une application.  
  
## Syntaxe  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinThread::CWinThread](../Topic/CWinThread::CWinThread.md)|Construit un objet `CWinThread`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md)|Commence l'exécution d'un objet d' `CWinThread` .|  
|[CWinThread::ExitInstance](../Topic/CWinThread::ExitInstance.md)|Substitution de nettoyage lorsque le thread s'arrête.|  
|[CWinThread::GetMainWnd](../Topic/CWinThread::GetMainWnd.md)|Extrait un pointeur vers la fenêtre principale du thread.|  
|[CWinThread::GetThreadPriority](../Topic/CWinThread::GetThreadPriority.md)|Obtient la priorité du thread actuel.|  
|[CWinThread::InitInstance](../Topic/CWinThread::InitInstance.md)|Substitution pour effectuer l'initialisation de l'instance du thread.|  
|[CWinThread::IsIdleMessage](../Topic/CWinThread::IsIdleMessage.md)|Contrôles pour les messages spéciaux.|  
|[CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md)|Substitution pour exécuter pendant le traitement des temps d'inactivité de thread spécifique.|  
|[CWinThread::PostThreadMessage](../Topic/CWinThread::PostThreadMessage.md)|Publie un message à un autre objet d' `CWinThread` .|  
|[CWinThread::PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|Messages de filtres pour qu'ils soient distribués aux fonctions Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](../Topic/CWinThread::ProcessMessageFilter.md)|Certains messages intercepte d'avant qu'ils atteignent l'application.|  
|[CWinThread::ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|Intercepte toutes les exceptions non gérées levées par le message et des gestionnaires de commandes du thread.|  
|[CWinThread::PumpMessage](../Topic/CWinThread::PumpMessage.md)|Contient la boucle de message du thread.|  
|[CWinThread::ResumeThread](../Topic/CWinThread::ResumeThread.md)|Décrémente le compteur de suspension d'un thread.|  
|[CWinThread::Run](../Topic/CWinThread::Run.md)|Opération de service pour les threads avec une pompe de messages.  Substitution pour personnaliser la boucle de message par défaut.|  
|[CWinThread::SetThreadPriority](../Topic/CWinThread::SetThreadPriority.md)|Définit la priorité du thread actuel.|  
|[CWinThread::SuspendThread](../Topic/CWinThread::SuspendThread.md)|Incrémente le compteur de suspension d'un thread.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinThread::operator HANDLE](../Topic/CWinThread::operator%20HANDLE.md)|Récupère le handle de l'objet d' `CWinThread` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinThread::m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md)|Spécifie si destruction de l'objet à l'abandon de thread.|  
|[CWinThread::m\_hThread](../Topic/CWinThread::m_hThread.md)|Handle du thread actuel.|  
|[CWinThread::m\_nThreadID](../Topic/CWinThread::m_nThreadID.md)|ID du thread actuel.|  
|[CWinThread::m\_pActiveWnd](../Topic/CWinThread::m_pActiveWnd.md)|Pointeur vers la fenêtre principale de l'application conteneur lorsqu'un OLE serveur est actif sur place.|  
|[CWinThread::m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md)|Contient un pointeur vers la fenêtre principale de l'application.|  
  
## Notes  
 Le thread principal de l'exécution est généralement fournie par un objet dérivé d' `CWinApp`; `CWinApp` est dérivé d' `CWinThread`.  Les objets supplémentaires d' `CWinThread` permettent aux threads dans une application donnée.  
  
 Il existe deux types généraux de threads qu' `CWinThread` prend en charge : threads de travail et threads d'interface utilisateur.  Les threads de travail n'ont pas de pompe de messages : par exemple, un thread qui effectue des calculs d'arrière\-plan dans une application de feuille de calcul.  Les threads d'interface utilisateur ont des messages d'une pompe de messages et de processus réception du système.  [CWinApp](../../mfc/reference/cwinapp-class.md) et les classes dérivés de lui sont des exemples de threads d'interface utilisateur.  D'autres threads d'interface utilisateur peuvent également être dérivés directement d' `CWinThread`.  
  
 Les objets de la classe `CWinThread` existent en général pendant la durée du thread.  Si vous souhaitez modifier ce comportement, définissez [m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md) à **FALSE**.  
  
 La classe d' `CWinThread` est nécessaire pour rendre votre code et MFC complètement thread\-safe.  Les données locales de thread utilisées par l'infrastructure pour mettre à jour les informations de thread spécifique par des objets d' `CWinThread` .  En raison de cette dépendance sur `CWinThread` pour traiter les données locales de thread, un thread qui utilise MFC doit être créé par MFC.  Par exemple, un thread créé par la fonction runtime [\_beginthread, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) ne peut utiliser aucune API MFC.  
  
 Pour créer un thread, appelez [AfxBeginThread](../Topic/AfxBeginThread.md).  Il existe deux formes, selon que vous souhaitez un ouvrier ou un thread d'interface utilisateur.  Si vous souhaitez un thread d'interface utilisateur, passez à `AfxBeginThread` un pointeur vers `CRuntimeClass` de votre `CWinThread`classe dérivée.  Si vous souhaitez créer un thread de travail, passez à `AfxBeginThread` un pointeur vers la fonction de contrôle et le paramètre à la fonction de contrôle.  Pour les deux threads de travail et threads d'interface utilisateur, vous pouvez spécifier les paramètres facultatifs qui modifient la priorité, la taille de la pile, les balises de création, les attributs de sécurité.  `AfxBeginThread` retourne un pointeur vers votre nouvel objet d' `CWinThread` .  
  
 Au lieu d'appeler `AfxBeginThread`, vous pouvez construire `CWinThread`objet dérivé puis appeler `CreateThread`.  Cette méthode à deux couches de construction est utile si vous souhaitez réutiliser l'objet d' `CWinThread` entre la création et les points consécutifs des opérations de thread.  
  
 Pour plus d'informations sur `CWinThread`, consultez les articles [Multithreading avec C\+\+ et MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Multithreading : Créer des threads d'interface utilisateur](../../parallel/multithreading-creating-user-interface-threads.md), [Multithreading : Création de threads de travail](../../parallel/multithreading-creating-worker-threads.md), et [Multithreading : Comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)