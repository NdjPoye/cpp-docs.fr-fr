---
title: "Itération de la Collection de bibliothèque C++ Standard en utilisant for each | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a4ce2de13380895f1f313559abeb87e4cd65db2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>Itération de la Collection de bibliothèque C++ Standard en utilisant for each
Le `for each` mot clé peut être utilisé pour itérer sur une collection de la bibliothèque C++ Standard.  
  
## <a name="all-platforms"></a>Toutes les plateformes  
 **Remarques**  
  
 Une collection de la bibliothèque C++ Standard est également appelé un *conteneur*. Pour plus d’informations, consultez [Conteneurs de la bibliothèque standard C++](../standard-library/stl-containers.md).  
  
## <a name="examples"></a>Exemples  
 **Exemple**  
  
 Le code suivant utilise des exemple `for each` d’itérer sur une [ \<carte >](../standard-library/map.md).  
  
```  
// for_each_stl.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
using namespace std;  
  
int main() {  
   int retval  = 0;  
   map<string, int> months;  
  
   months["january"] = 31;  
   months["february"] = 28;  
   months["march"] = 31;  
   months["april"] = 30;  
   months["may"] = 31;  
   months["june"] = 30;  
   months["july"] = 31;  
   months["august"] = 31;  
   months["september"] = 30;  
   months["october"] = 31;  
   months["november"] = 30;  
   months["december"] = 31;  
  
   map<string, int> months_30;  
  
   for each( pair<string, int> c in months )  
      if ( c.second == 30 )  
         months_30[c.first] = c.second;  
  
   for each( pair<string, int> c in months_30 )  
      retval++;  
  
   cout << "Months with 30 days = " << retval << endl;  
}  
```  
  
 **Sortie**  
  
```Output  
Months with 30 days = 4  
```  
  
 **Exemple**  
  
 L’exemple de code suivant utilise une référence const (`const&`) pour une variable d’itération avec des conteneurs de bibliothèque C++ Standard. Vous pouvez utiliser une référence (`&`) en tant qu’une variable d’itération sur une collection d’un type qui peut être déclaré comme un *T*`&`.  
  
```  
// for_each_stl_2.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
using namespace std;  
  
int main() {  
   int retval = 0;  
  
   vector<int> col(3);  
   col[0] = 10;  
   col[1] = 20;  
   col[2] = 30;  
  
   for each( const int& c in col )  
      retval += c;  
  
   cout << "retval: " << retval << endl;  
}  
```  
  
 **Sortie**  
  
```Output  
retval: 60  
```  
  
## <a name="windows-runtime"></a>Windows Runtime  
 **Remarques**  
  
 Il n’existe aucune note spécifique à la plateforme sur cette fonctionnalité.  
  
### <a name="requirements"></a>Spécifications  
 Option du compilateur : **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Remarques**  
  
 Il n’existe aucune note spécifique à la plateforme sur cette fonctionnalité.  
  
### <a name="requirements"></a>Spécifications  
 Option du compilateur : **/clr**  
  
## <a name="see-also"></a>Voir aussi  
 [pour chacune, dans](../dotnet/for-each-in.md)   
 [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)