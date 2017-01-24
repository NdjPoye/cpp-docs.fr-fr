---
title: "range_error, classe | Microsoft Docs"
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
  - "stdexcept/std::range_error"
  - "std.range_error"
  - "range_error"
  - "std::range_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_error (classe)"
ms.assetid: 8afb3e88-fc49-4213-b096-ed63d7aea37c
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# range_error, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe qui sert de classe de base pour toutes les exceptions levées pour signaler une erreur de plage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class range_error : public runtime_error {  
public:  
    explicit range_error(const string& message);

    explicit range_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Remarques  
 La valeur retournée par [que](../standard-library/exception-class1.md) est une copie de **message**`.`[données](../standard-library/basic-string-class.md#basic_string__data).  
  
## <a name="example"></a>Exemple  
  
```  
// range_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
using namespace std;  
int main()  
{  
   try   
   {  
      throw range_error( "The range is in error!" );  
   }  
   catch (exception &e)   
   {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught: The range is in error!  
Type: class std::range_error  
*\  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< stdexcept>  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
 [runtime_error, classe](../standard-library/runtime-error-class.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

