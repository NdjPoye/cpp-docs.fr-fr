---
title: "API WRL principales par cat&#233;gorie | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 7367bacf-6b7c-4ecd-a0ce-a662db46fc66
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# API WRL principales par cat&#233;gorie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les tableaux suivants répertorient principal [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] classes, structures, fonctions et macros. Constructions dans les classes et les espaces de noms d’assistance sont omises. Ces listes complètent la documentation de l’API, organisée par espace de noms.  
  
### <a name="classes"></a>Classes  
  
|Titre|Description|  
|-----------|-----------------|  
|[ActivationFactory (classe)](../windows/activationfactory-class.md)|Permet à une ou plusieurs classes d'être activées par le Windows Runtime.|  
|[AsyncBase (classe)](../windows/asyncbase-class.md)|Implémente la machine d'état asynchrone du Windows Runtime.|  
|[ClassFactory (classe)](../windows/classfactory-class.md)|Implémente les fonctionnalités de base de l'interface `IClassFactory`.|  
|[ComPtr (classe)](../windows/comptr-class.md)|Crée un type de *pointeur intelligent* représentant l'interface spécifiée par le paramètre de modèle. ComPtr met à jour automatiquement un décompte de références pour le pointeur d'interface sous-jacent et libère l'interface quand le décompte de références atteint zéro.|  
|[Classe d’événements (Windows Runtime C++ STL)](../windows/event-class-windows-runtime-cpp-template-library.md)|Représente un événement.|  
|[EventSource (classe)](../windows/eventsource-class.md)|Représente un événement. Les fonctions membres d'`EventSource` ajoutent, suppriment et appellent des gestionnaires d'événements.|  
|[FtmBase (classe)](../windows/ftmbase-class.md)|Représente un objet marshaler libre de threads.|  
|[HandleT (classe)](../windows/handlet-class.md)|Représente un handle d’un objet.|  
|[Hstring, classe](../windows/hstring-class.md)|Prend en charge HSTRING poignées de manipulation.|  
|[Hstringreference, classe](../windows/hstringreference-class.md)|Représente une chaîne HSTRING créé à partir d’une chaîne existante.|  
|[Module (classe)](../windows/module-class.md)|Représente une collection d’objets connexes.|  
|[Module::genericreleasenotifier, classe](../windows/module-genericreleasenotifier-class.md)|Appelle un gestionnaire d’événements lorsque le dernier objet du module en cours est libéré. Le Gestionnaire d’événements est spécifié par sur une expression lambda, le functor ou le pointeur de fonction.|  
|[Module::methodreleasenotifier, classe](../windows/module-methodreleasenotifier-class.md)|Appelle un gestionnaire d’événements lorsque le dernier objet du module en cours est libéré. Le Gestionnaire d’événements est spécifié par un objet et son membre pointeur de méthode.|  
|[Module::releasenotifier, classe](../windows/module-releasenotifier-class.md)|Appelle un gestionnaire d’événements lorsque le dernier objet dans un module est lancé.|  
|[Roinitializewrapper, classe](../windows/roinitializewrapper-class.md)|Initialise la [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[RuntimeClass (classe)](../windows/runtimeclass-class.md)|Représente une classe instanciée qui hérite du nombre spécifié d'interfaces et fournit le Windows Runtime spécifié, le COM classique et la prise en charge de références faibles.|  
|[SimpleActivationFactory (classe)](../windows/simpleactivationfactory-class.md)|Fournit un mécanisme fondamental pour créer une classe de base Windows Runtime ou une classe de base COM classique.|  
|[SimpleClassFactory (classe)](../windows/simpleclassfactory-class.md)|Fournit un mécanisme fondamental pour créer une classe de base.|  
|[WeakRef (classe)](../windows/weakref-class.md)|Représente un *référence faible* qui peut être utilisé par seulement le Windows Runtime, com pas classique. Une référence faible représente un objet qui peut être accessible ou non.|  
  
### <a name="structures"></a>Structures  
  
|Titre|Description|  
|-----------|-----------------|  
|[ChainInterfaces (Structure)](../windows/chaininterfaces-structure.md)|Spécifie les fonctions de vérification et d'initialisation pouvant être appliquées à un ensemble d'ID d'interface.|  
|[CloakedIid (Structure)](../windows/cloakediid-structure.md)|Indique à le `RuntimeClass`, `Implements` et `ChainInterfaces` que l’interface spécifiée n’est pas accessible dans la liste de l’IID de modèles.|  
|[Implements (Structure)](../windows/implements-structure.md)|Implémente `QueryInterface` et `GetIid` pour les interfaces spécifiées.|  
|[MixIn (Structure)](../windows/mixin-structure.md)|Garantit qu'une classe d'exécution dérive des interfaces du Windows Runtime, le cas échéant, puis des interfaces du COM classique.|  
  
### <a name="functions"></a>Fonctions  
  
|Titre|Description|  
|-----------|-----------------|  
|[ActivateInstance (fonction)](../windows/activateinstance-function.md)|Enregistre et récupère une instance d’un type spécifié défini dans un code de classe spécifiée.|  
|[AsWeak (fonction)](../windows/asweak-function.md)|Récupère une référence faible à une instance spécifiée.|  
|[Fonction de rappel](../windows/callback-function-windows-runtime-cpp-template-library.md)|Crée un objet dont la fonction membre est une méthode de rappel.|  
|[CreateActivationFactory (fonction)](../windows/createactivationfactory-function.md)|Crée une fabrique qui produit des instances de la classe spécifiée pouvant être activées par le Windows Runtime.|  
|[CreateClassFactory (fonction)](../windows/createclassfactory-function.md)|Crée une fabrique produisant des instances de la classe spécifiée.|  
|[GetActivationFactory (fonction)](../windows/getactivationfactory-function.md)|Récupère une fabrique d’activation pour le type spécifié par le paramètre de modèle.|  
|[Make, fonction](../windows/make-function.md)|Initialise la classe [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] spécifiée.|  
  
### <a name="macros"></a>Macros  
  
|Titre|Description|  
|-----------|-----------------|  
|[Activatableclass, Macros](../windows/activatableclass-macros.md)|Remplit un cache interne qui contient une fabrique qui peut créer une instance de la classe spécifiée.|  
|[Inspectableclass, Macro](../windows/inspectableclass-macro.md)|Définit le niveau de confiance et de nom de la classe runtime.|  
  
## <a name="see-also"></a>Voir aussi  
 [Windows Runtime bibliothèque de modèles C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)