---
title: "Portabilité aux limites ABI (Modern C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 06cb6c97580b4c4c9a6c961cb76f2c4d84d841ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="portability-at-abi-boundaries-modern-c"></a>Portabilité aux limites ABI (Modern C++)
Utiliser des types suffisamment portables et les conventions aux limites de l’interface binaire. Un « type portable » est un type intégré de C ou un struct qui contient uniquement des types intégrés C. Classe types peuvent uniquement être utilisés lors de l’appelant et l’appelé s’accorder sur mise en page, l’appel convention, etc. Ceci est possible uniquement lorsque les deux sont compilés avec le compilateur et les paramètres de compilateur.  
  
## <a name="how-to-flatten-a-class-for-c-portability"></a>Comment faire pour lisser une classe pour la portabilité de C  
 Lorsque les appelants peuvent être compilés avec un autre compilateur/langage, les « aplatir » à un **extern « C »** API avec une convention d’appel spécifique :  
  
```cpp  
// class widget {  
//   widget();  
//   ~widget();  
//   double method( int, gadget& );  
// };  
extern "C" {        // functions using explicit "this"  
   struct widget;   // opaque type (forward declaration only)  
   widget* STDCALL widget_create();      // constructor creates new "this"  
   void STDCALL widget_destroy(widget*); // destructor consumes "this"  
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Bienvenue dans C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Bibliothèque C++ standard](../standard-library/cpp-standard-library-reference.md)