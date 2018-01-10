---
title: logic_error, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdexcept/std::logic_error
dev_langs: C++
helpviewer_keywords: logic_error class
ms.assetid: b290d73d-94e1-4288-af86-2bb5d71f677a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9f5afb57135d5358bc22496668dee6a91b23efd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="logicerror-class"></a>logic_error, classe
Classe qui sert de classe de base pour toutes les exceptions levées pour signaler des erreurs normalement détectables avant l'exécution du programme, telles que les violations de conditions préalables logiques.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class logic_error : public exception {  
public:  
    explicit logic_error(const string& message);

    explicit logic_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Notes  
 La valeur retournée par [what](../standard-library/exception-class.md) est une copie de **message**`.`[data](../standard-library/basic-string-class.md#data).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// logic_error.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      throw logic_error( "logic error" );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught: " << e.what( ) << endl;  
      cerr << "Type: " << typeid( e ).name( ) << endl;  
   };  
}  
```  
  
 **Sortie**  
  
```  
Caught: logic error  
Type: class std::logic_error  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<stdexcept>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
[exception, classe](../standard-library/exception-class.md)  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

