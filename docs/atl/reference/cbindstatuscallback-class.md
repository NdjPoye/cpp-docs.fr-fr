---
title: "CBindStatusCallback Class | Microsoft Docs"
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
  - "CBindStatusCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous data transfer [C++]"
  - "CBindStatusCallback class"
  - "data transfer [C++]"
  - "data transfer [C++], asynchrones"
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBindStatusCallback Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente l'interface `IBindStatusCallback`.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <class   
      T  
      , int   
      nBindFlags  
      = BINDF_ASYNCHRONOUS |   
BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx  
<T::_ThreadModel::ThreadModelNoCS>, public IBindStatusCallbackImpl<T>   
```  
  
#### Paramètres  
 `T`  
 Votre classe qui contient la fonction qui est appelée comme données est reçue.  
  
 *nBindFlags*  
 Spécifie des indicateurs de liaison qui sont retournées par [GetBindInfo](../Topic/CBindStatusCallback::GetBindInfo.md).  L'implémentation par défaut affecte à la liaison pour être asynchrone, récupère la version la plus récente des données\/objet, et ne stocke pas les données extraites dans le cache disque.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](../Topic/CBindStatusCallback::CBindStatusCallback.md)|Constructeur.|  
|[CBindStatusCallback::~CBindStatusCallback](../Topic/CBindStatusCallback::~CBindStatusCallback.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBindStatusCallback::Download](../Topic/CBindStatusCallback::Download.md)|Méthode statique qui commence l'opération de téléchargement, crée un objet d' `CBindStatusCallback` , et appelle `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](../Topic/CBindStatusCallback::GetBindInfo.md)|Appelé par le moniker asynchrone pour demander des informations sur le type de liaison à créer.|  
|[CBindStatusCallback::GetPriority](../Topic/CBindStatusCallback::GetPriority.md)|Appelé par le moniker asynchrone pour obtenir la priorité de l'opération de liaison.  L'implémentation ATL retourne `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](../Topic/CBindStatusCallback::OnDataAvailable.md)|Appelé pour fournir des données à votre application comme elle devient disponible.  Lit les données, puis appelle la fonction qui lui est passée pour utiliser les données.|  
|[CBindStatusCallback::OnLowResource](../Topic/CBindStatusCallback::OnLowResource.md)|Appelée lorsque les ressources sont insuffisantes.  L'implémentation ATL retourne `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](../Topic/CBindStatusCallback::OnObjectAvailable.md)|Appelé par le moniker asynchrone pour passer un pointeur d'interface de l'objet à votre application.  L'implémentation ATL retourne `S_OK`.|  
|[CBindStatusCallback::OnProgress](../Topic/CBindStatusCallback::OnProgress.md)|Appelé pour indiquer la progression d'un processus de téléchargement de données.  L'implémentation ATL retourne `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](../Topic/CBindStatusCallback::OnStartBinding.md)|Appelé lorsque la liaison est démarré.|  
|[CBindStatusCallback::OnStopBinding](../Topic/CBindStatusCallback::OnStopBinding.md)|Appelé lorsque le transfert de données asynchrone est arrêté.|  
|[CBindStatusCallback::StartAsyncDownload](../Topic/CBindStatusCallback::StartAsyncDownload.md)|Initialise les octets disponibles et les octets lisent à zéro, créez un objet de flux de type transmission de type push d'une URL, et appellent `OnDataAvailable` chaque fois que les données sont disponibles.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBindStatusCallback::m\_dwAvailableToRead](../Topic/CBindStatusCallback::m_dwAvailableToRead.md)|Nombre d'octets disponibles à lire.|  
|[CBindStatusCallback::m\_dwTotalRead](../Topic/CBindStatusCallback::m_dwTotalRead.md)|Nombre total d'octets lus.|  
|[CBindStatusCallback::m\_pFunc](../Topic/CBindStatusCallback::m_pFunc.md)|Pointeur vers une fonction appelée lorsque les données sont disponibles.|  
|[CBindStatusCallback::m\_pT](../Topic/CBindStatusCallback::m_pT.md)|Pointeur vers l'objet demandant le transfert de données asynchrone.|  
|[CBindStatusCallback::m\_spBindCtx](../Topic/CBindStatusCallback::m_spBindCtx.md)|Pointeur vers l'interface d' [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) pour l'opération de liaison actuelle.|  
|[CBindStatusCallback::m\_spBinding](../Topic/CBindStatusCallback::m_spBinding.md)|Pointeur vers l'interface d' `IBinding` pour l'opération de liaison actuelle.|  
|[CBindStatusCallback::m\_spMoniker](../Topic/CBindStatusCallback::m_spMoniker.md)|Pointeur vers l'interface d' [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) pour que l'URL à utiliser.|  
|[CBindStatusCallback::m\_spStream](../Topic/CBindStatusCallback::m_spStream.md)|Pointeur vers l'interface d' [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) pour le transfert de données.|  
  
## Notes  
 La classe `CBindStatusCallback` implémente l'interface `IBindStatusCallback`.  `IBindStatusCallback` doit être implémenté par votre application pour qu'elle peut recevoir des notifications d'un transfert de données asynchrone.  Le moniker asynchrone fourni par le système utilise les méthodes d' `IBindStatusCallback` pour envoyer et recevoir des informations sur la migration de données asynchrone à partir de votre objet.  
  
 En général, l'objet d' `CBindStatusCallback` est associé à une opération de liaison spécifique.  Par exemple, dans l'exemple de [ASYNC](../../top/visual-cpp-samples.md) , lorsque vous affectez à la propriété URL, il crée un objet d' `CBindStatusCallback` dans l'appel à `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/CPP/cbindstatuscallback-class_1.h)]  
  
 Le moniker asynchrone utilise la fonction de rappel `OnData` pour appeler votre application lorsqu'il a des données.  Le moniker asynchrone est fourni par le système.  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)