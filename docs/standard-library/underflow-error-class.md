---
title: "underflow_error, classe | Microsoft Docs"
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
  - "stdexcept/std::underflow_error"
  - "underflow_error"
  - "std.underflow_error"
  - "std::underflow_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underflow_error (classe)"
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# underflow_error, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe qui sert de classe de base pour toutes les exceptions levées pour signaler un dépassement de capacité arithmétique négatif.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class underflow_error : public runtime_error {  
public:  
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Remarques  
 La valeur retournée par [que](../standard-library/exception-class1.md) est une copie de **message**`.`[données](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Exemple  
  
```  
// underflow_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      throw underflow_error( "The number's a bit small, captain!" );  
   }  
   catch ( exception &e ) {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught: The number's a bit small, captain!  
Type: class std::underflow_error  
*\  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< stdexcept>  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
 [\< stdexcept> membres](http://msdn.microsoft.com/fr-fr/7b6b0a73-916e-44aa-9a3f-f5b6b3ce98e6)   
 [runtime_error, classe](../standard-library/runtime-error-class.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

