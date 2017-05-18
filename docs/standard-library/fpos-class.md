---
title: fpos, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::fpos
- fpos
- ios/std::fpos::seekpos
- ios/std::fpos::state
- ios/std::fpos::operator streamoff
dev_langs:
- C++
helpviewer_keywords:
- fpos class, about fpos class
- fpos class
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: dfa9ee908b89c94b2eea95c450f67ca71031cf45
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="fpos-class"></a>fpos, classe
La classe de modèle décrit un objet qui peut stocker toutes les informations nécessaires à la restauration d'un indicateur de position de fichier arbitraire dans n'importe quel flux. Un objet de classe fpos\< **St**> stocke au moins deux objets membres :  
  
-   Un décalage d’octet de type [streamoff](../standard-library/ios-typedefs.md#streamoff).  
  
-   Un état de conversion utilisable par un objet de classe basic_filebuf de type **St**, généralement `mbstate_t`.  
  
 Il peut également stocker une position de fichier arbitraire, utilisable par un objet de classe [basic_filebuf](../standard-library/basic-filebuf-class.md) de type `fpos_t`. Cependant, pour un environnement avec une taille de fichier limitée, `streamoff` et `fpos_t` peuvent parfois être utilisés de manière interchangeable. Pour un environnement où aucun flux de données n'a un encodage de dépendance d'état, `mbstate_t` peut être inutilisé. Ainsi, le nombre d'objets membres stockés peut varier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Statetype>  
class fpos  
```  
  
#### <a name="parameters"></a>Paramètres  
 *Statetype*  
 Informations d'état.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[fpos](#fpos)|Créer un objet qui contient des informations sur une position (offset) dans un flux.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[seekpos](#seekpos)|Utilisée uniquement en interne par la bibliothèque C++ Standard. N'appelez pas cette méthode à partir de votre code.|  
|[state](#state)|Définit ou retourne l'état de la conversion.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator!=](#op_neq)|Teste l'inégalité d'indicateurs de position de fichier.|  
|[operator+](#op_add)|incrémente un indicateur de position de fichier.|  
|[operator+=](#op_add_eq)|incrémente un indicateur de position de fichier.|  
|[operator-](#operator-)|Décrémente un indicateur de position de fichier.|  
|[operator-=](#operator-_eq)|Décrémente un indicateur de position de fichier.|  
|[operator==](#op_eq_eq)|Teste l'égalité d'indicateurs de position de fichier.|  
|[operator streamoff](#op_streamoff)|Convertit un objet de type `fpos` en objet de type `streamoff`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<ios>  
  
 **Espace de noms :** std  
  
##  <a name="fpos"></a>  fpos::fpos  
 Créer un objet qui contient des informations sur une position (offset) dans un flux.  
  
```  
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage dans le flux.  
  
 `_State`  
 État de départ de l’objet `fpos`.  
  
 *_Filepos*  
 Décalage dans le flux.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur stocke le décalage `_Off` par rapport au début du fichier et dans l’état de conversion initial (si c’est important). Si `_Off` est -1, l’objet résultant représente une position de flux non valide.  
  
 Le deuxième constructeur stocke un décalage de zéro et l’objet `_State`.  
  
##  <a name="op_neq"></a>  fpos::operator!=  
 Teste l'inégalité d'indicateurs de position de fichier.  
  
```  
bool operator!=(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Indicateur de position de fichier à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les indicateurs de position de fichier ne sont pas égaux, sinon **false**.  
  
### <a name="remarks"></a>Remarques  
 La fonction membre retourne `!(*this == right)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// fpos_op_neq.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   fpos<int> pos1, pos2;  
   ifstream file;  
   char c;  
  
   // Compare two fpos object  
   if ( pos1 != pos2 )  
      cout << "File position pos1 and pos2 are not equal" << endl;  
   else  
      cout << "File position pos1 and pos2 are equal" << endl;  
  
   file.open( "fpos_op_neq.txt" );  
   file.seekg( 0 );   // Goes to a zero-based position in the file  
   pos1 = file.tellg( );  
   file.get( c);  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 += 1;  
   file.get( c );  
   cout << c << endl;  
  
   pos1 = file.tellg( ) - fpos<int>( 2);  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 = pos1 + fpos<int>( 1 );  
   file.get(c);  
   cout << c << endl;  
  
   pos1 -= fpos<int>( 2 );  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   file.close( );  
}  
```  
  
##  <a name="op_add"></a>  fpos::operator+  
 incrémente un indicateur de position de fichier.  
  
```  
fpos<Statetype> operator+(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage duquel vous voulez incrémenter l’indicateur de position de fichier.  
  
### <a name="return-value"></a>Valeur de retour  
 Position dans le fichier.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne **fpos(\*this) +=** `_Off`.  
  
### <a name="example"></a>Exemple  
  Consultez [operator!=](#op_neq) pour obtenir un exemple d’utilisation de `operator+`.  
  
##  <a name="op_add_eq"></a>  fpos::operator+=  
 incrémente un indicateur de position de fichier.  
  
```  
fpos<Statetype>& operator+=(streamoff _Off);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage duquel vous voulez incrémenter l’indicateur de position de fichier.  
  
### <a name="return-value"></a>Valeur de retour  
 Position dans le fichier.  
  
### <a name="remarks"></a>Notes  
 La fonction membre ajoute `_Off` à l’objet membre de décalage stocké et retourne ensuite **\*this**. Pour le positionnement dans un fichier, le résultat est généralement valide uniquement pour les flux binaires qui n’ont pas de codage dépendant de l’état.  
  
### <a name="example"></a>Exemple  
  Consultez [operator!=](#op_neq) pour obtenir un exemple d’utilisation de `operator+=`.  
  
##  <a name="fpos__operator-"></a>  fpos::operator-  
 Décrémente un indicateur de position de fichier.  
  
```  
streamoff operator-(const fpos<Statetype>& right) const;
 
fpos<Statetype> operator-(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Position du fichier.  
  
 `_Off`  
 Décalage du flux.  
  
### <a name="return-value"></a>Valeur de retour  
 La première fonction membre retourne `(streamoff)*this - (streamoff) right`. La deuxième fonction membre retourne `fpos(*this) -= _Off`.  
  
### <a name="example"></a>Exemple  
  Consultez [operator!=](#op_neq) pour obtenir un exemple d’utilisation de `operator-`.  
  
##  <a name="fpos__operator-_eq"></a>  fpos::operator-=  
 Décrémente un indicateur de position de fichier.  
  
```  
fpos<Statetype>& operator-=(streamoff _Off);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Off`  
 Décalage du flux.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre retourne `fpos(*this) -= _Off`.  
  
### <a name="remarks"></a>Remarques  
 Pour le positionnement dans un fichier, le résultat est généralement valide uniquement pour les flux binaires qui n’ont pas de codage dépendant de l’état.  
  
### <a name="example"></a>Exemple  
  Consultez [operator!=](#op_neq) pour obtenir un exemple d’utilisation de `operator-=`.  
  
##  <a name="op_eq_eq"></a>  fpos::operator==  
 Teste l'égalité d'indicateurs de position de fichier.  
  
```  
bool operator==(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Indicateur de position de fichier à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les indicateurs de position de fichier sont égaux, sinon **false**.  
  
### <a name="remarks"></a>Remarques  
 La fonction membre retourne `(streamoff)*this == (streamoff)right`.  
  
### <a name="example"></a>Exemple  
  Consultez [operator!=](#op_neq) pour obtenir un exemple d’utilisation de `operator+=`.  
  
##  <a name="op_streamoff"></a>  fpos::operator streamoff  
 Convertit un objet de type `fpos` en objet de type `streamoff`.  
  
```  
operator streamoff() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’objet membre de décalage stocké et tout décalage supplémentaire stocké dans le cadre de l’objet membre `fpos_t`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// fpos_op_streampos.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   streamoff s;  
   ofstream file( "rdbuf.txt");  
  
   fpos<mbstate_t> f = file.tellp( );  
   // Is equivalent to ..  
   // streampos f = file.tellp( );  
   s = f;  
   cout << s << endl;  
}  
```  
  
```Output  
0  
```  
  
##  <a name="seekpos"></a>  fpos::seekpos  
 Cette méthode est uniquement utilisée en interne par la bibliothèque C++ Standard. N'appelez pas cette méthode à partir de votre code.  
  
```  
fpos_t seekpos() const;
```  
  
##  <a name="state"></a>  fpos::state  
 Définit ou retourne l'état de la conversion.  
  
```  
Statetype state() const;

void state(Statetype _State);
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 Nouvel état de conversion.  
  
### <a name="return-value"></a>Valeur de retour  
 État de conversion.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre retourne la valeur stockée dans l’objet membre **St**. La deuxième fonction de membre stocke `_State` dans l’objet membre **St**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// fpos_state.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main() {  
   using namespace std;  
   streamoff s;  
   ifstream file( "fpos_state.txt" );  
  
   fpos<mbstate_t> f = file.tellg( );  
   char ch;  
   while ( !file.eof( ) )  
      file.get( ch );  
   s = f;  
   cout << f.state( ) << endl;  
   f.state( 9 );  
   cout << f.state( ) << endl;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)


