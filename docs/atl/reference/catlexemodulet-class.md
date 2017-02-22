---
title: "CAtlExeModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlExeModuleT<T>"
  - "CAtlExeModuleT"
  - "ATL.CAtlExeModuleT<T>"
  - "ATL::CAtlExeModuleT"
  - "ATL.CAtlExeModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlExeModuleT class"
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAtlExeModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente le package pour une application.  
  
## Syntaxe  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlExeModuleT :  
   public CAtlModuleT< T >  
```  
  
#### Paramètres  
 `T`  
 Votre classe dérivée d' `CAtlExeModuleT`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](../Topic/CAtlExeModuleT::CAtlExeModuleT.md)|Constructeur.|  
|[CAtlExeModuleT::~CAtlExeModuleT](../Topic/CAtlExeModuleT::~CAtlExeModuleT.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlExeModuleT::InitializeCom](../Topic/CAtlExeModuleT::InitializeCom.md)|Initialise COM.|  
|[CAtlExeModuleT::ParseCommandLine](../Topic/CAtlExeModuleT::ParseCommandLine.md)|Analyse la ligne de commande et exécute l'inscription si nécessaire.|  
|[CAtlExeModuleT::PostMessageLoop](../Topic/CAtlExeModuleT::PostMessageLoop.md)|Cette méthode est appelée juste après les sorties de boucle de message.|  
|[CAtlExeModuleT::PreMessageLoop](../Topic/CAtlExeModuleT::PreMessageLoop.md)|Cette méthode est appelée juste avant écrire la boucle de message.|  
|[CAtlExeModuleT::RegisterClassObjects](../Topic/CAtlExeModuleT::RegisterClassObjects.md)|Stocke l'objet de classe.|  
|[CAtlExeModuleT::RevokeClassObjects](../Topic/CAtlExeModuleT::RevokeClassObjects.md)|Révoque l'objet de classe.|  
|[CAtlExeModuleT::Run](../Topic/CAtlExeModuleT::Run.md)|Cette méthode exécute le code dans le module EXE pour initialiser, exécute la boucle de message, et nettoie.|  
|[CAtlExeModuleT::RunMessageLoop](../Topic/CAtlExeModuleT::RunMessageLoop.md)|Cette méthode exécute la boucle de message.|  
|[CAtlExeModuleT::UninitializeCom](../Topic/CAtlExeModuleT::UninitializeCom.md)|Uninitializes COM.|  
|[CAtlExeModuleT::Unlock](../Topic/CAtlExeModuleT::Unlock.md)|Décrémente le nombre de verrous du module.|  
|[CAtlExeModuleT::WinMain](../Topic/CAtlExeModuleT::WinMain.md)|Cette méthode implémente le code nécessaire pour exécuter un EXE.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md)|Une balise qui indique qu'il doit y a un délai en envoyant le module.|  
|[CAtlExeModuleT::m\_dwPause](../Topic/CAtlExeModuleT::m_dwPause.md)|Une valeur de pause utilisée pour vérifier tous les objets sont libérées avant l'arrêt.|  
|[CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md)|Une valeur de délai d'attente utilisée pour différer le déchargement du module.|  
  
## Notes  
 `CAtlExeModuleT` représente le package pour une application \(EXE\) et contient le code qui prend en charge la création d'un EXE, le traitement de la ligne de commande, stocker des objets de classe, exécuter la boucle de message, puis nettoyer sur la sortie.  
  
 Cette classe est conçue pour améliorer les performances quand les objets COM dans le serveur de fichiers exécutables sont constamment créés et détruits.  Après le dernier objet COM est relâché, le fichier EXE attend une durée spécifiée par le membre de [CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md) .  S'il n'existe aucune activité pendant cette période \(autrement dit, aucun objet COM n'est créé\), le processus d'arrêt est initialisé.  
  
 Le membre de [CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md) est une balise utilisée pour déterminer si le fichier EXE utilise le mécanisme défini ci\-dessus.  S'il a la valeur false, le module s'arrêtera immédiatement.  
  
 Pour plus d'informations sur les modules dans ATL, consultez [Classes de module ATL](../../atl/atl-module-classes.md).  
  
## Hiérarchie d'héritage  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Exemple ATLDuck](../../top/visual-cpp-samples.md)   
 [CAtlModuleT Class](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT Class](../../atl/reference/catldllmodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)