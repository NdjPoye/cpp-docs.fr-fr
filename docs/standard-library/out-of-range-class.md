---
title: "out_of_range, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "out_of_range"
  - "stdexcept/std::out_of_range"
  - "std.out_of_range"
  - "std::out_of_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out_of_range (classe)"
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# out_of_range, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un argument qui est en dehors de sa plage valide.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class out_of_range : public logic_error {  
public:  
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};  
```  
  
## <a name="remarks"></a>Remarques  
 La valeur retournée par [que](../standard-library/exception-class1.md) est une copie de **message**`.`[données](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Exemple  
  
```  
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
 **En-tête :** \< stdexcept>  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
 [logic_error, classe](../standard-library/logic-error-class.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

