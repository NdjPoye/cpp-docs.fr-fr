---
title: runtime_error, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdexcept/std::runtime_error
dev_langs:
- C++
helpviewer_keywords:
- runtime_error class
ms.assetid: 4d0227bf-847b-45a2-a320-2351ebf98368
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: fffdedc184df2de8956341015345bf2f6fb16e80
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="runtimeerror-class"></a>runtime_error, classe
Classe qui sert de classe de base pour toutes les exceptions levées pour signaler des erreurs normalement détectables uniquement durant l'exécution du programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class runtime_error : public exception {  
public:  
    explicit runtime_error(const string& message);

    explicit runtime_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Notes  
 La valeur retournée par la [classe exception](../standard-library/exception-class.md) est une copie de **message**`.`[data](../standard-library/basic-string-class.md#data).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// runtime_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
// runtime_error  
   try   
   {  
      locale loc( "test" );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught bad locale name  
Type class std::runtime_error  
*\  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<stdexcept>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
[exception, classe](../standard-library/exception-class.md)

    
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


