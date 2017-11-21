---
title: out_of_range, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdexcept/std::out_of_range
dev_langs: C++
helpviewer_keywords: out_of_range class
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aec90b22bf3423ea93ae3ea5115dfd6b20a14c40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="outofrange-class"></a>out_of_range, classe
Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un argument qui est en dehors de sa plage valide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class out_of_range : public logic_error {  
public:  
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};  
```  
  
## <a name="remarks"></a>Notes  
 La valeur retournée par [what](../standard-library/exception-class.md) est une copie de **message**`.`[data](../standard-library/basic-string-class.md#data).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// out_of_range.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
int main() {  
// out_of_range  
   try {  
      string str( "Micro" );  
      string rstr( "soft" );  
      str.append( rstr, 5, 3 );  
      cout << str << endl;  
   }  
   catch ( exception &e ) {  
      cerr << "Caught: " << e.what( ) << endl;  
   };  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
Caught: invalid string position  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<stdexcept>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [logic_error, classe](../standard-library/logic-error-class.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

