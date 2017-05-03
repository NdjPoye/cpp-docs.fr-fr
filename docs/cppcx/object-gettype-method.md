---
title: "Object::GetType, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetType"
ms.assetid: f633d71a-ff80-49f9-931d-189c00b1f6c5
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetType, m&#233;thode
Retourne un objet [Platform::Type](../cppcx/platform-type-class.md) qui décrit le type de runtime d'un objet.  
  
## Syntaxe  
  
```vb  
Object::GetType()  
```  
  
```csharp  
  
```  
  
## Valeur de propriété\/valeur de retour  
 Objet [Platform::Type](../cppcx/platform-type-class.md) qui décrit le type de runtime de l'objet.  
  
## Notes  
 La [Type::GetTypeCode Method](../cppcx/type-gettypecode-method.md) statique peut être utilisée pour obtenir une valeur [Platform::TypeCode \(énumération\)](../cppcx/platform-typecode-enumeration.md) qui représente le type actuel. Ceci est particulièrement utile pour les types intégrés. Le code de type pour toute classe ref en plus de [Platform::String](../cppcx/platform-string-class.md) est Object \(1\).  
  
 La classe [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) est utilisée dans les API Windows comme une méthode indépendante du langage pour passer des informations de type entre les composants et les applications Windows. La [Platform::Type \(classe\)](../cppcx/platform-type-class.md) a des opérateurs de conversion entre `Type` et `TypeName`.  
  
 Utilisez l'opérateur [typeid](~/windows/typeid-cpp-component-extensions.md) pour retourner un objet `Platform::Type` pour un nom de classe, par exemple en naviguant entre les pages XAML :  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## Voir aussi  
 [Platform::Type \(classe\)](../cppcx/platform-type-class.md)   
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)   
 [système de type](../cppcx/type-system-c-cx.md)