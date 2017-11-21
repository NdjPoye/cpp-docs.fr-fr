---
title: Runtimeclass, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass
dev_langs: C++
helpviewer_keywords: RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e757712b360ff3ed4de12d8236c75a691a1f0c7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclass-class"></a>RuntimeClass, classe
Représente une classe instanciée qui hérite du nombre spécifié d'interfaces et fournit le Windows Runtime spécifié, le COM classique et la prise en charge de références faibles.  
  
 Vous dérivez généralement à partir de vos types de WRL `RuntimeClass` , car cette classe implémente `AddRef`, `Release`, et `QueryInterface`, et vous aide à gérer le nombre de références global du module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
class RuntimeClass : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT, RuntimeClassFlags<WinRt>>;  
  
template <  
   unsigned int classFlags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
class RuntimeClass<RuntimeClassFlags<classFlags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT, RuntimeClassFlags<classFlags> >;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `I0`  
 L’ID d’interface de zéro. (Obligatoire)  
  
 `I1`  
 Le premier ID d’interface. (facultatif)  
  
 `I2`  
 Le deuxième ID d’interface. (facultatif)  
  
 `I3`  
 L’ID d’interface tiers. (facultatif)  
  
 `I4`  
 La quatrième ID d’interface. (facultatif)  
  
 `I5`  
 La cinquième ID d’interface. (facultatif)  
  
 `I6`  
 La sixième ID d’interface. (facultatif)  
  
 `I7`  
 La septième ID d’interface. (facultatif)  
  
 `I8`  
 L’ID d’interface huitième. (facultatif)  
  
 `I9`  
 La neuvième ID d’interface. (facultatif)  
  
 `classFlags`  
 Une combinaison d’une ou plusieurs [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) valeurs d’énumération.  Le `__WRL_CONFIGURATION_LEGACY__` (macro) peut être définie pour modifier la valeur par défaut de classFlags pour toutes les classes d’exécution dans le projet. S’il est défini, les instances de RuntimeClass sont non agiles par défaut de dy. Quand ne pas défini, les instances de RuntimeClass sont agiles par défaut. Pour éviter toute ambiguïté spécifiez toujours le RuntimeClassType::FtmBase ou RuntimeClassType::InhibitFtmBase.
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass, constructeur](../windows/runtimeclass-runtimeclass-constructor.md)|Initialise l’instance actuelle de la classe RuntimeClass.|  
|[RuntimeClass::~RuntimeClass, destructeur](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Désinitialise l’instance actuelle de la classe RuntimeClass.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `RuntimeClass`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)
