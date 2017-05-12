---
title: "Boxing (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# Boxing (C++/CX)
Le *boxing* est l’encapsulation d’une variable de type valeur, telle que [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx) ou de type scalaire fondamental tel que `int` dans une classe ref quand la variable est passée à une méthode qui accepte [Platform::Object^](../cppcx/platform-object-class.md) comme son type d’entrée.  
  
## Passer un type valeur à un paramètre Object^  
 Bien que vous ne deviez pas convertir par boxing une variable explicitement pour la passer à un paramètre de méthode de type [Platform::Object^](../cppcx/platform-object-class.md), vous devez caster explicitement vers le type d'origine lorsque vous récupérez des valeurs qui ont été précédemment converties par boxing.  
  
 [!code-cpp[cx_boxing#01](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.cpp#01)]  
  
### Utilisation de Platform::IBox\<T\> pour prendre en charge des types valeur Nullable  
 C\# et Visual Basic prennent en charge le concept des types valeur autorisant la valeur Null. Dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], vous pouvez utiliser le type `Platform::IBox<T>` pour exposer des méthodes publiques qui prennent en charge les paramètres de type valeur autorisant la valeur Null. L'exemple suivant présente une méthode publique [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] qui retourne la valeur null lorsqu'un appelant C\# passe la valeur null pour un des arguments.  
  
 [!code-cpp[cx_boxing#02](../snippets/cpp/VS_Snippets_Misc/cx_boxing/cpp/class1.h#02)]  
  
 Dans un client C\# XAML, vous pouvez l'utiliser comme suit :  
  
```  
  
// C# client code BoxingDemo.Class1 obj = new BoxingDemo.Class1(); int? a = null; int? b = 5; var result = obj.Multiply(a,b); //result = null  
  
```  
  
## Voir aussi  
 [Système de type \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Effectuer un cast \(C\+\+\/CX\)](../cppcx/casting-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)