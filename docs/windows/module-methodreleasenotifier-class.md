---
title: "Module::MethodReleaseNotifier, classe | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::MethodReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MethodReleaseNotifier (classe)"
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::MethodReleaseNotifier, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelle un gestionnaire d’événements lorsque le dernier objet du module en cours est libéré. Le Gestionnaire d’événements est spécifié par un objet et son membre pointeur de méthode.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<  
   typename T  
>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de l’objet dont la fonction membre est le Gestionnaire d’événements.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Constructeur de module::MethodReleaseNotifier::MethodReleaseNotifier](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Initialise une nouvelle instance de la classe Module::MethodReleaseNotifier.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier :: Invoke (méthode)](../windows/module-methodreleasenotifier-invoke-method.md)|Appelle le Gestionnaire d’événements associé à l’objet Module::MethodReleaseNotifier en cours.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[Membre de données module::MethodReleaseNotifier::method_](../windows/module-methodreleasenotifier-method-data-member.md)|Contient un pointeur vers le Gestionnaire d’événements pour l’objet Module::MethodReleaseNotifier en cours.|  
|[Membre de données module::MethodReleaseNotifier::object_](../windows/module-methodreleasenotifier-object-data-member.md)|Contient un pointeur vers l’objet dont la fonction membre est le Gestionnaire d’événements pour l’objet Module::MethodReleaseNotifier en cours.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)