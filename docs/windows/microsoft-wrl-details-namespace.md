---
title: "Microsoft::WRL::Details, espace de noms | Microsoft Docs"
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
ms.assetid: d71fe149-d804-4c6f-961d-43fe21ef8630
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Microsoft::WRL::Details, espace de noms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l’infrastructure/FAO et n’est pas destinée à être utilisée directement à partir de votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace Microsoft::WRL::Details;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="classes"></a>Classes  
  
|Nom|Description|  
|----------|-----------------|  
|[ComPtrRef (classe)](../windows/comptrref-class.md)|Représente une référence à un objet de type ComPtr \< T>.|  
|[ComPtrRefBase (classe)](../windows/comptrrefbase-class.md)|Représente la classe de base pour le [ComPtrRef](../windows/comptrref-class.md) (classe).|  
|[DontUseNewUseMake (classe)](../windows/dontusenewusemake-class.md)|Empêche l’utilisation d’opérateur `new` dans `RuntimeClass`. Par conséquent, vous devez utiliser le [fonction](../windows/make-function.md) à la place.|  
|[EventTargetArray (classe)](../windows/eventtargetarray-class.md)|Représente un tableau des gestionnaires d’événements.|  
|[MakeAllocator (classe)](../windows/makeallocator-class.md)|Alloue de la mémoire pour une classe activable, avec ou sans prise en charge de la référence faible.|  
|[ModuleBase (classe)](../windows/modulebase-class.md)|Représente la classe de base de la [Module](../windows/module-class.md) classes.|  
|[Removeiunknown, classe](../windows/removeiunknown-class.md)|Crée un type qui est équivalent à une `IUnknown`-type de base, mais a non virtuelle `QueryInterface`, `AddRef`, et `Release` méthodes.|  
|[WeakReference (classe)](../windows/weakreference-class1.md)|Représente un *référence faible* qui peut être utilisé avec le Windows Runtime ou COM classique. Une référence faible représente un objet qui peut être accessible ou non.|  
  
### <a name="structures"></a>Structures  
  
|Nom|Description|  
|----------|-----------------|  
|[ArgTraits (Structure)](../windows/argtraits-structure.md)|Déclare un délégué spécifié interface et une fonction membre anonyme qui a un nombre spécifié de paramètres.|  
|[ArgTraitsHelper (Structure)](../windows/argtraitshelper-structure.md)|Permet de définir les caractéristiques communes d’arguments du délégué.|  
|[BoolStruct (Structure)](../windows/boolstruct-structure.md)|Définit si un ComPtr gère la durée de vie d’une interface. BoolStruct est utilisé en interne par le [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) (opérateur).|  
|[CreatorMap (Structure)](../windows/creatormap-structure.md)|Contient des informations sur l’initialisation, enregistrer et annuler l’inscription d’objets.|  
|[DerefHelper (Structure)](../windows/derefhelper-structure.md)|Représente un pointeur déréférencé vers le `T*` paramètre de modèle.|  
|[EnableIf (Structure)](../windows/enableif-structure.md)|Définit un membre de données du type spécifié par le deuxième paramètre de modèle, si le premier paramètre de modèle a la valeur `true`.|  
|[FactoryCache (Structure)](../windows/factorycache-structure.md)|Contient l’emplacement d’une fabrique de classe et une valeur qui identifie un [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ou un objet de classe COM.|  
|[ImplementsBase (Structure)](../windows/implementsbase-structure.md)|Permet de valider des types de paramètre de modèle dans [implémente Structure](../windows/implements-structure.md).|  
|[ImplementsHelper (Structure)](../windows/implementshelper-structure.md)|Permet d’implémenter le [implémente](../windows/implements-structure.md) structure.|  
|[InterfaceList (Structure)](../windows/interfacelist-structure.md)|Permet de créer une liste récursive des interfaces.|  
|[InterfaceListHelper (Structure)](../windows/interfacelisthelper-structure.md)|Crée un `InterfaceList` type en appliquant les arguments de paramètre de modèle spécifié de manière récursive.|  
|[InterfaceTraits (Structure)](../windows/interfacetraits-structure.md)|Caractéristiques communes d’implémente d’une interface.|  
|[InvokeHelper (Structure)](../windows/invokehelper-structure.md)|Fournit une implémentation de la méthode Invoke() selon le nombre spécifié et le type d’arguments.|  
|[IsBaseOfStrict (Structure)](../windows/isbaseofstrict-structure.md)|Teste si un type est la base d'un autre.|  
|[IsSame (Structure)](../windows/issame-structure.md)|Teste si un type spécifié est identique à un autre de type spécifié.|  
|[Nil, Structure](../windows/nil-structure.md)|Permet d’indiquer un paramètre de modèle non spécifié, facultatif.|  
|[RemoveReference (Structure)](../windows/removereference-structure.md)|Supprime la caractéristique de référence ou une référence rvalue à partir du paramètre de modèle de classe spécifiée.|  
|[Runtimeclassbase, Structure](../windows/runtimeclassbase-structure.md)|Permet de détecter `RuntimeClass` dans les [rendre](../windows/make-function.md) (fonction).|  
|[Runtimeclassbaset, Structure](../windows/runtimeclassbaset-structure.md)|Fournit des méthodes d’assistance pour `QueryInterface` lors de l’obtention des ID d’interface et les opérations.|  
|[VerifyInheritanceHelper (Structure)](../windows/verifyinheritancehelper-structure.md)|Teste si une interface est dérivée d’une autre interface.|  
|[VerifyInterfaceHelper (Structure)](../windows/verifyinterfacehelper-structure.md)|Vérifie que l’interface spécifiée par le paramètre de modèle répond à certaines exigences.|  
  
### <a name="enumerations"></a>Énumérations  
  
|Nom|Description|  
|----------|-----------------|  
|[Asyncstatusinternal, énumération](../windows/asyncstatusinternal-enumeration.md)|Spécifie un mappage entre des énumérations internes de l’état des opérations asynchrones et la **Windows::Foundation::AsyncStatus** (énumération).|  
  
### <a name="functions"></a>Fonctions  
  
|Nom|Description|  
|----------|-----------------|  
|[ActivationFactoryCallback (fonction)](../windows/activationfactorycallback-function.md)|Obtient la fabrique d’activation pour le code d’activation spécifié.|  
|[Move (fonction)](../windows/move-function.md)|Déplace l’argument spécifié d’un emplacement à un autre.|  
|[RaiseException (fonction)](../windows/raiseexception-function.md)|Lève une exception dans le thread appelant.|  
|[Swap (fonction) (Windows Runtime C++ STL)](../windows/swap-function-windows-runtime-cpp-template-library.md)|Échange les valeurs des deux arguments spécifiés.|  
|[TerminateMap (fonction)](../windows/terminatemap-function.md)|Arrête les fabriques de classe dans le module spécifié.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** async.h, client.h, corewrappers.h, event.h, ftm.h, implements.h, internal.h, module.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [Microsoft::wrl::wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)