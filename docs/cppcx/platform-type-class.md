---
title: "Platform::Type (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Type (classe)"
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Type (classe)
Contient des informations d'exécution sur un type, en particulier un nom de chaîne et un code de type. Obtenu en appelant [Object::GetType Method](../cppcx/object-gettype-method.md) sur un objet ou en utilisant l'opérateur [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) sur un nom de classe ou de construction.  
  
## Syntaxe  
  
```cpp  
public ref class Platform::Type :      Platform::Object,      Platform::Details::IEquatable,      Platform::Details::IPrintable  
```  
  
## Notes  
 La classe `Type` est utile dans les applications qui doivent effectuer un traitement en utilisant une instruction `if` ou `switch` qui crée une branche en fonction du type d'exécution d'un objet. Le code de type qui décrit la catégorie d'un type est récupéré à l'aide de la fonction membre [Type::GetTypeCode Method](../cppcx/type-gettypecode-method.md).  
  
## Méthodes publiques  
  
|||  
|-|-|  
|[Type::GetTypeCode Method](../cppcx/type-gettypecode-method.md)|Retourne une valeur [Platform::TypeCode Enumeration](../cppcx/platform-typecode-enumeration.md) pour l'objet.|  
  
## Propriétés publiques  
  
|||  
|-|-|  
|[Type::FullName, propriété](../cppcx/type-fullname-property.md)|Retourne une [classe Platform::String](../cppcx/platform-string-class.md)^ qui représente le nom complet du type et utilise . \(le point\) comme séparateur au lieu de :: \(le double deux\-points\), par exemple MyNamespace.MyClass.|  
  
## Opérateurs de conversion  
  
|||  
|-|-|  
|[Type^, opérateur](../cppcx/operator-subtracttype-hat.md)|Permet de convertir `Windows::UI::Xaml::Interop::TypeName` en `Platform::Type`.|  
|[Windows::UI::Xaml::Interop::TypeName, opérateur](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|Permet de convertir `Platform::Type` en `Windows::UI::Xaml::Interop::TypeName`.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)