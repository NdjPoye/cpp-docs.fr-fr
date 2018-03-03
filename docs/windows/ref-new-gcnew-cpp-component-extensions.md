---
title: gcnew de nouveau, ref (Extensions du composant C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 616117f7274d6f68456aa23614fb354a71982fb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new, gcnew  (extensions du composant C++)
Le `ref new` mot clé d’agrégation alloue une instance d’un type qui est le garbage collecté lors de l’objet devienne inaccessible, et qui retourne un handle ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) vers l’objet alloué.  
  
## <a name="all-runtimes"></a>Tous les runtimes  
 La mémoire d'une instance d'un type alloué par `ref new` est automatiquement désallouée.  
  
 Une opération `ref new` lève une exception `OutOfMemoryException` s'il est impossible d'allouer de la mémoire.  
  
 Pour plus d’informations sur la façon dont la mémoire pour les types natifs C++ est allouée et désallouée, consultez [le nouveau et supprimer des opérateurs](../cpp/new-and-delete-operators.md).  
  
## <a name="windows-runtime"></a>Windows Runtime  
 Utilisez `ref new` pour allouer de la mémoire aux objets Windows Runtime dont vous voulez administrer automatiquement la durée de vie. L'objet est automatiquement désalloué quand son nombre de références atteint zéro, ce qui se produit une fois que la dernière copie de la référence est hors de portée. Pour plus d’informations, consultez [les classes ou structures](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Configuration requise  
 Option du compilateur : **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 La mémoire d'un type managé (type référence ou valeur) est allouée par `gcnew`, puis désallouée à l'aide du garbage collection.  
  
### <a name="requirements"></a>Configuration requise  
 Option du compilateur : **/clr**  
  
### <a name="examples"></a>Exemples  
 **Exemple**  
  
 L'exemple suivant utilise `gcnew` pour allouer un objet Message.  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **Exemple**  
  
 L'exemple suivant utilise `gcnew` pour créer un type valeur boxed à utiliser comme type référence.  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **Sortie**  
  
```Output  
32  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)