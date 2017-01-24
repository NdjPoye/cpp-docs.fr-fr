---
title: "Module::ReleaseNotifier, classe | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::ReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseNotifier (classe)"
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::ReleaseNotifier, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelle un gestionnaire d’événements lorsque le dernier objet dans un module est lancé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Module::ReleaseNotifier :: ~ ReleaseNotifier, destructeur](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Deinitializes l’instance actuelle de la classe Module::ReleaseNotifier.|  
|[Constructeur de module::ReleaseNotifier::ReleaseNotifier](../windows/module-releasenotifier-releasenotifier-constructor.md)|Initialise une nouvelle instance de la classe Module::ReleaseNotifier.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Module::ReleaseNotifier :: Invoke (méthode)](../windows/module-releasenotifier-invoke-method.md)|En cas d’implémentation, appelle un gestionnaire d’événements lorsque le dernier objet dans un module est lancé.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Supprime l’objet Module::ReleaseNotifier en cours si l’objet a été construit avec un paramètre `true`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)