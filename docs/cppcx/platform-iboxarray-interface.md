---
title: Platform::iboxarray, Interface | Documents Microsoft
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs: C++
helpviewer_keywords: Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 421f8517b8a96c40bb44dd959eba90b1bf903113
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray, interface
`IBoxArray` est le wrapper pour les tableaux de types valeur passés via l'interface binaire d'application (ABI) ou stockés dans les collections d'éléments `Platform::Object^` tels que ceux dans les contrôles XAML.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type de la valeur boxed dans chaque élément du tableau.  
  
### <a name="remarks"></a>Notes  
 `IBoxArray`est le C + c++ / nom CX pour `Windows::Foundation::IReferenceArray`.  
  
### <a name="members"></a>Membres  
 L'interface `IBoxArray` hérite de l'interface `IValueType` . `IBoxArray` a également ces membres :  
  
|Méthode|Description|  
|------------|-----------------|  
|[Valeur](#value)|Retourne le tableau non converti par boxing qui a été précédemment enregistré dans cette instance `IBoxArray` .|  

## <a name="value"></a>Iboxarray::value, propriété
Retourne la valeur qui a été enregistrée à l'origine dans cet objet.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Type de la valeur boxed.  
  
### <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 Retourne la valeur qui a été enregistrée à l'origine dans cet objet.  
  
### <a name="remarks"></a>Notes  
 Pour obtenir un exemple, consultez [Boxing](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>Voir aussi  
 [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)