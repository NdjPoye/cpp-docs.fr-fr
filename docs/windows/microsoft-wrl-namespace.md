---
title: "Microsoft::WRL, espace de noms | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL"
  - "module/Microsoft::WRL"
  - "async/Microsoft::WRL"
  - "internal/Microsoft::WRL"
  - "event/Microsoft::WRL"
  - "ftm/Microsoft::WRL"
  - "client/Microsoft::WRL"
  - "corewrappers/Microsoft::WRL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WRL (espace de noms)"
ms.assetid: 01118a8f-f564-4859-b87e-9444848585a1
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Microsoft::WRL, espace de noms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les types fondamentaux qui constituent la [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace Microsoft::WRL;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="typedefs"></a>Typedef  
  
|Nom|Description|  
|----------|-----------------|  
|`InhibitWeakReferencePolicy`|`RuntimeClassFlags<WinRt &#124; InhibitWeakReference>`|  
  
### <a name="classes"></a>Classes  
  
|Nom|Description|  
|----------|-----------------|  
|[ActivationFactory (classe)](../windows/activationfactory-class.md)|Permet à une ou plusieurs classes d'être activées par le Windows Runtime.|  
|[AsyncBase (classe)](../windows/asyncbase-class.md)|Implémente la machine d'état asynchrone du Windows Runtime.|  
|[ClassFactory (classe)](../windows/classfactory-class.md)|Implémente les fonctionnalités de base de l'interface `IClassFactory`.|  
|[ComPtr (classe)](../windows/comptr-class.md)|Crée un type de *pointeur intelligent* représentant l'interface spécifiée par le paramètre de modèle. ComPtr met à jour automatiquement un décompte de références pour le pointeur d'interface sous-jacent et libère l'interface quand le décompte de références atteint zéro.|  
|[DeferrableEventArgs (classe)](../windows/deferrableeventargs-class.md)|Classe de modèle utilisée pour les types d’arguments des événements différés.|  
|[EventSource (classe)](../windows/eventsource-class.md)|Représente un événement. Les fonctions membres d'`EventSource` ajoutent, suppriment et appellent des gestionnaires d'événements.|  
|[FtmBase (classe)](../windows/ftmbase-class.md)|Représente un objet marshaler libre de threads.|  
|[Module (classe)](../windows/module-class.md)|Représente une collection d’objets connexes.|  
|[RuntimeClass (classe)](../windows/runtimeclass-class.md)|Représente une classe instanciée qui hérite du nombre spécifié d'interfaces et fournit le Windows Runtime spécifié, le COM classique et la prise en charge de références faibles.|  
|[SimpleActivationFactory (classe)](../windows/simpleactivationfactory-class.md)|Fournit un mécanisme fondamental pour créer une classe de base Windows Runtime ou une classe de base COM classique.|  
|[SimpleClassFactory (classe)](../windows/simpleclassfactory-class.md)|Fournit un mécanisme fondamental pour créer une classe de base.|  
|[WeakRef (classe)](../windows/weakref-class.md)|Représente un *référence faible* qui peut être utilisé par seulement le Windows Runtime, com pas classique. Une référence faible représente un objet qui peut être accessible ou non.|  
  
### <a name="structures"></a>Structures  
  
|Nom|Description|  
|----------|-----------------|  
|[ChainInterfaces (Structure)](../windows/chaininterfaces-structure.md)|Spécifie les fonctions de vérification et d'initialisation pouvant être appliquées à un ensemble d'ID d'interface.|  
|[CloakedIid (Structure)](../windows/cloakediid-structure.md)|Indique aux modèles RuntimeClass, Implements et ChainInterfaces que l'interface spécifiée n'est pas accessible dans la liste des IID.|  
|[Implements (Structure)](../windows/implements-structure.md)|Implémente QueryInterface et GetIid pour les interfaces spécifiées.|  
|[MixIn (Structure)](../windows/mixin-structure.md)|Garantit qu'une classe d'exécution dérive des interfaces du Windows Runtime, le cas échéant, puis des interfaces du COM classique.|  
|[RuntimeClassFlags (Structure)](../windows/runtimeclassflags-structure.md)|Contient le type d’une instance d’un [RuntimeClass](../windows/runtimeclass-class.md).|  
  
### <a name="enumerations"></a>Énumérations  
  
|Nom|Description|  
|----------|-----------------|  
|[Asyncresulttype, énumération](../windows/asyncresulttype-enumeration.md)|Spécifie le type de résultat retourné par la méthode GetResults().|  
|[ModuleType, énumération](../windows/moduletype-enumeration.md)|Spécifie si un module doit prendre en charge un serveur in-process ou un serveur out-of-process.|  
|[Runtimeclasstype, énumération](../windows/runtimeclasstype-enumeration.md)|Spécifie le type de [RuntimeClass](../windows/runtimeclass-class.md) instance qui est pris en charge.|  
  
### <a name="functions"></a>Fonctions  
  
|Nom|Description|  
|----------|-----------------|  
|[AsWeak (fonction)](../windows/asweak-function.md)|Récupère une référence faible à une instance spécifiée.|  
|[Fonction de rappel](../windows/callback-function-windows-runtime-cpp-template-library.md)|Crée un objet dont la fonction membre est une méthode de rappel.|  
|[CreateActivationFactory (fonction)](../windows/createactivationfactory-function.md)|Crée une fabrique qui produit des instances de la classe spécifiée pouvant être activées par le Windows Runtime.|  
|[CreateClassFactory (fonction)](../windows/createclassfactory-function.md)|Crée une fabrique produisant des instances de la classe spécifiée.|  
|[Make, fonction](../windows/make-function.md)|Initialise la classe [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] spécifiée.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::wrl::wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)