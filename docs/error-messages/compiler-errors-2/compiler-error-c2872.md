---
title: Erreur du compilateur C2872 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: d53dbd9429ba3c1a525b85a3ef9f2e70152ddfa2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2872"></a>Erreur du compilateur C2872
'symbole' : symbole ambigu  
  
Le compilateur ne peut pas déterminer le symbole auquel vous faites référence à.  
  
C2872 peut se produire si un fichier d’en-tête comprend une [à l’aide de la directive](../../cpp/namespaces-cpp.md#using_directives)et un fichier d’en-tête suivant est inclus et il contient un type qui se trouve également dans l’espace de noms spécifié dans la `using` directive. Spécifiez un `using` directive que lorsque tous vos fichiers d’en-tête sont spécifiées avec `#include`.  
  
 Pour plus d’informations sur C2872, voir les articles de la Base de connaissances [PRB : compilateur erreurs lorsque vous utilisez #import avec XML dans Visual C++ .NET](http://support.microsoft.com/kb/316317) et [» erreur C2872 : 'Plate-forme' : symbole ambigu « message d’erreur lorsque vous utilisez l’espace de noms Windows::Foundation::Metadata dans Visual Studio 2013](https://support.microsoft.com/kb/2890859).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2872 :  
  
```cpp  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```
