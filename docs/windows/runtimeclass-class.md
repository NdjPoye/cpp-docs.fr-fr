---
title: "RuntimeClass, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClass (classe)"
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RuntimeClass, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente une classe instanciée qui hérite du nombre spécifié d'interfaces, et fournit le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]spécifié, COM classique, et la prise en charge de références faibles.  
  
 Vous dérivez généralement vos types WRL de `RuntimeClass`, car cette classe implémente `AddRef`, `Release` et `QueryInterface`, et aide à gérer le nombre total de références du module.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `I0`  
 Le zérotième ID d'interface. \(Obligatoire\)  
  
 `I1`  
 Le premier ID d'interface. \(facultatif\)  
  
 `I2`  
 Le deuxième ID d'interface. \(facultatif\)  
  
 `I3`  
 Le troisième ID d'interface. \(facultatif\)  
  
 `I4`  
 Quatrième ID d'interface. \(facultatif\)  
  
 `I5`  
 Le cinquième ID d'interface. \(facultatif\)  
  
 `I6`  
 Le sixième ID d'interface. \(facultatif\)  
  
 `I7`  
 Le septième ID d'interface. \(facultatif\)  
  
 `I8`  
 Huitième ID d'interface. \(facultatif\)  
  
 `I9`  
 Le neuvième ID d'interface. \(facultatif\)  
  
 `classFlags`  
 Une combinaison d'une ou plusieurs valeurs d'énumération [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[RuntimeClass::RuntimeClass, constructeur](../windows/runtimeclass-runtimeclass-constructor.md)|Initialise l'instance actuelle de la classe RuntimeClass.|  
|[RuntimeClass::~RuntimeClass, destructeur](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Libère l'instance actuelle de la classe RuntimeClass.|  
  
## Hiérarchie d'héritage  
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
  
## Configuration requise  
 **En\-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)