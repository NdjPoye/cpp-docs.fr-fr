---
title: Boxing (C + c++ / CX) | Documents Microsoft
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: cefc2ccd44efc089749414702667a4e13ec3f630
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="boxing-ccx"></a>Boxing (C++/CX)
Le*boxing* est l’encapsulation d’une variable de type valeur, telle que [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)ou de type scalaire fondamental tel que `int`dans une classe ref quand la variable est passée à une méthode qui accepte [Platform::Object^](../cppcx/platform-object-class.md) comme son type d’entrée.  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Passer un type valeur à un paramètre Object^  
 Bien que vous ne deviez pas convertir par boxing une variable explicitement pour la passer à un paramètre de méthode de type [Platform::Object^](../cppcx/platform-object-class.md), vous devez caster explicitement vers le type d'origine lorsque vous récupérez des valeurs qui ont été précédemment converties par boxing.  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Utilisation de Platform::IBox\<T > pour prendre en charge des types valeur nullable  
 C# et Visual Basic prennent en charge le concept des types valeur autorisant la valeur Null. Dans C + c++ / CX, vous pouvez utiliser la `Platform::IBox<T>` type pour exposer des méthodes publiques qui prennent en charge les paramètres de type valeur nullable. L’exemple suivant montre un C + c++ / méthode publique CX qui retourne la valeur null lorsqu’un appelant c# passe la valeur null pour un des arguments.  
  
 [!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]  
  
 Dans un client C# XAML, vous pouvez l'utiliser comme suit :  
  
```  
  
// C# client code  
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();  
    int? a = null;  
    int? b = 5;  
    var result = obj.Multiply(a,b); //result = null  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Système de type (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Cast (C + c++ / CX)](../cppcx/casting-c-cx.md)   
 [Référence du langage Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence des espaces de noms](../cppcx/namespaces-reference-c-cx.md)