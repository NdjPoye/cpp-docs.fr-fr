---
title: "Platform::IBox, interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBox"
dev_langs: 
  - "C++"
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBox, interface
L'interface [Platform::IBox](../cppcx/platform-ibox-interface.md) est le nom C\+\+ de l'interface `Windows::Foundation::IReference`.  
  
## Syntaxe  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### Paramètres  
 `T`  
 Type de la valeur boxed.  
  
## Notes  
 L'interface `IBox<T>` est principalement utilisée en interne pour représenter les types de valeur Nullable, comme décrit dans [Classes et structs value \(C\+\+\/CX\)](../cppcx/value-classes-and-structs-c-cx.md). L'interface est aussi utilisée en interne pour effectuer un boxing des types valeur passés aux méthodes C\+\+ qui prennent des paramètres de type `Object^`. Vous pouvez déclarer explicitement un paramètre d'entrée comme `IBox<SomeValueType>`. Pour obtenir un exemple, consultez [Boxing](../cppcx/boxing-c-cx.md).  
  
## Configuration requise  
  
## Membres  
 L'interface `Platform::IBox` hérite de l'interface [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md).`IBox` a ces membres :  
  
 **Propriétés**  
  
|Méthode|Description|  
|-------------|-----------------|  
|Valeur|Retourne une valeur unboxed qui a été précédemment enregistrée dans cette instance `IBox`.|  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)