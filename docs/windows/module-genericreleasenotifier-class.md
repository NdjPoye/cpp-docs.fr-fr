---
title: "Module::GenericReleaseNotifier, classe | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::GenericReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GenericReleaseNotifier (classe)"
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::GenericReleaseNotifier, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelle un gestionnaire d’événements lorsque le dernier objet du module en cours est libéré. Le Gestionnaire d’événements est spécifié par sur une expression lambda, le functor ou le pointeur de fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<  
   typename T  
>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type du membre de données qui contient l’emplacement du Gestionnaire d’événements.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Constructeur de module::GenericReleaseNotifier::GenericReleaseNotifier](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Initialise une nouvelle instance de la classe Module::GenericReleaseNotifier.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier :: Invoke (méthode)](../windows/module-genericreleasenotifier-invoke-method.md)|Appelle le Gestionnaire d’événements associé à l’objet Module::GenericReleaseNotifier en cours.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[Membre de données module::GenericReleaseNotifier::callback_](../windows/module-genericreleasenotifier-callback-data-member.md)|Contient l’expression lambda, functor ou pointeur vers une fonction gestionnaire associé à l’objet Module::GenericReleaseNotifier en cours.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL
 
 ## <a name="see-also"></a>Voir aussi
 [Module (classe)](../windows/module-class.md)