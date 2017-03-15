---
title: '&lt;ios&gt;, typedefs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d9f9dd5f13f0f4559455ff8d8cf09bab5350b1f0
ms.lasthandoff: 02/24/2017

---
# <a name="ltiosgt-typedefs"></a>&lt;ios&gt;, typedefs
||||  
|-|-|-|  
|[ios](#ios)|[streamoff](#streamoff)|[streampos](#streampos)|  
|[streamsize](#streamsize)|[wios](#wios)|[wstreampos](#wstreampos)|  
  
##  <a name="a-nameiosa--ios"></a><a name="ios"></a>  ios  
 Prend en charge la classe ios de l'ancienne bibliothèque iostream.  
  
```  
typedef basic_ios<char, char_traits<char>> ios;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ios](../standard-library/basic-ios-class.md), spécialisée pour les éléments de type `char` ayant les caractéristiques par défaut.  
  
##  <a name="a-namestreamoffa--streamoff"></a><a name="streamoff"></a>  streamoff  
 Prend en charge les opérations internes.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamoff;  
#else  
    typedef long streamoff;  
#endif  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un entier signé qui décrit un objet capable de stocker un décalage d’octet impliqué dans différentes opérations de positionnement de flux. Sa représentation a au moins 32 bits de valeur. Elle n’est pas nécessairement assez grande pour représenter une position d’octet arbitraire dans un flux. La valeur **streamoff(-1)** indique généralement un décalage erroné.  
  
##  <a name="a-namestreamposa--streampos"></a><a name="streampos"></a>  streampos  
 Contient la position actuelle du pointeur de mémoire tampon ou du pointeur de fichier.  
  
```  
typedef fpos<mbstate_t> streampos;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ios_streampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
  
   ofstream x( "iostream.txt" );  
   x << "testing";  
   streampos y = x.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
##  <a name="a-namestreamsizea--streamsize"></a><a name="streamsize"></a>  streamsize  
 Indique la taille du flux.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamsize;  
#else  
    typedef int streamsize;  
#endif  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un entier signé qui décrit un objet capable de stocker le nombre d’éléments impliqués dans différentes opérations de flux. Sa représentation a au moins 16 bits. Elle n’est pas nécessairement assez grande pour représenter une position d’octet arbitraire dans un flux.  
  
### <a name="example"></a>Exemple  
  Après avoir compilé et exécuté le programme suivant, examinez le fichier test.txt pour voir l’effet du paramètre `streamsize`.  
  
```  
// ios_streamsize.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   char a[16] = "any such text";  
   ofstream x( "test.txt" );  
   streamsize y = 6;  
   x.write( a, y );  
}  
```  
  
##  <a name="a-namewiosa--wios"></a><a name="wios"></a>  wios  
 Prend en charge la classe wios de l'ancienne bibliothèque iostream.  
  
```  
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de la classe de modèle [basic_ios](../standard-library/basic-ios-class.md), spécialisée pour les éléments de type `wchar_t` ayant les caractéristiques par défaut.  
  
##  <a name="a-namewstreamposa--wstreampos"></a><a name="wstreampos"></a>  wstreampos  
 Contient la position actuelle du pointeur de mémoire tampon ou du pointeur de fichier.  
  
```  
typedef fpos<mbstate_t> wstreampos;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme de [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// ios_wstreampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   wofstream xw( "wiostream.txt" );  
   xw << L"testing";  
   wstreampos y = xw.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<ios>](../standard-library/ios.md)


