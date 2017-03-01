---
title: auto_ptr, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::auto_ptr
- std.auto_ptr
- auto_ptr
- memory/std::auto_ptr
dev_langs:
- C++
helpviewer_keywords:
- auto_ptr class
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 92da9cbca9d7594bcb740d70fb57ce453d769e17
ms.lasthandoff: 02/24/2017

---
# <a name="autoptr-class"></a>auto_ptr, classe
Encapsule un pointeur intelligent autour d’une ressource qui garantit que celle-ci est détruite automatiquement quand le contrôle quitte un bloc.  
  
 La classe `unique_ptr` plus performante remplace `auto_ptr`. Pour plus d’informations, consultez [unique_ptr, classe](../standard-library/unique-ptr-class.md).  
  
 Pour plus d’informations sur `throw()` et sur la gestion des exceptions, consultez [Spécifications d’exceptions (throw)](../cpp/exception-specifications-throw-cpp.md).  
  
## <a name="syntax"></a>Syntaxe  
 ```   
class auto_ptr {
public:
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```  
#### <a name="parameters"></a>Paramètres  
 ` right`  
 `auto_ptr` à partir duquel obtenir une ressource existante.  
  
 ` ptr`  
 Pointeur spécifié pour remplacer le pointeur stocké.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle décrit un pointeur intelligent, appelé `auto_ptr,` pour un objet alloué. Le pointeur doit avoir la valeur null ou désigner un objet alloué par `new`. Le `auto_ptr` transfère la propriété si sa valeur stockée est assignée à un autre objet. (Il remplace la valeur stockée après un transfert avec un pointeur null.) Le destructeur de `auto_ptr<Type>` supprime l'objet alloué. Le `auto_ptr<Type>` garantit qu'un objet alloué est supprimé automatiquement quand le contrôle quitte un bloc, même suite à la levée d'une exception. Vous ne devez pas construire deux objets `auto_ptr<Type>` qui possèdent le même objet.  
  
 Vous pouvez passer un objet `auto_ptr<Type>` par valeur en tant qu'argument à un appel de fonction. Un `auto_ptr` ne peut pas être un élément d'un conteneur de bibliothèque STL. Vous ne pouvez pas gérer de manière fiable une séquence d’objets `auto_ptr<Type>` avec un conteneur de bibliothèque C++ Standard.  
  
## <a name="members"></a>Membres  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[auto_ptr](#auto_ptr__auto_ptr)|Constructeur des objets de type `auto_ptr`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[element_type](#auto_ptr__element_type)|Le type est un synonyme du paramètre de modèle `Type`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[get](#auto_ptr__get)|La fonction membre retourne le pointeur stocké `myptr`.|  
|[release](#auto_ptr__release)|Le membre remplace le pointeur stocké `myptr` par un pointeur null et il retourne le pointeur stocké précédemment.|  
|[reset](#auto_ptr__reset)|La fonction membre évalue l'expression `deleteÂ myptr`, mais uniquement si la valeur de pointeur stocké `myptr` change suite à l'appel de fonction. Elle remplace ensuite le pointeur stocké par `ptr`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator=](#auto_ptr__operator_eq)|Opérateur d'assignation qui transfère la propriété d'un objet `auto_ptr` à un autre.|  
|[operator*](#auto_ptr__operator_star)|Opérateur de déréférencement pour les objets de type `auto_ptr`.|  
|[operator->](#auto_ptr__operator-_gt_)|Opérateur pour autoriser l'accès aux membres.|  
|[operator auto_ptr\<Other>](#auto_ptr__operator_auto_ptr_lt_other_gt_)|Effectue un cast d'un type de `auto_ptr` vers un autre type de `auto_ptr`.|  
|[operator auto_ptr_ref\<Other>](#auto_ptr__operator_auto_ptr_ref_lt_other_gt_)|Effectue un cast d'un `auto_ptr` vers un `auto_ptr_ref`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<memory>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameautoptrautoptra--autoptrautoptr"></a><a name="auto_ptr__auto_ptr"></a>  auto_ptr::auto_ptr  
 Constructeur des objets de type `auto_ptr`.  
  
```   
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>  
auto _ptr(auto _ptr<Other>& right) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 ` ptr`  
 Pointeur vers l’objet que `auto_ptr` encapsule.  
  
 ` right`  
 L’objet `auto_ptr` doit être copié par le constructeur.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur stocke ` ptr` dans **myptr**, le pointeur stocké vers l’objet alloué. Le deuxième constructeur transfère la propriété du pointeur stocké dans ` right` en stockant ` right`. [release](#auto_ptr__release) dans **myptr**.  
  
 Le troisième constructeur se comporte comme le deuxième, il stocke **right**. `ref`. **release** dans **myptr**, où `ref` est la référence stockée dans ` right`.  
  
 Le constructeur de modèle a le même comportement que le deuxième constructeur, à condition qu’un pointeur vers **Other** puisse être implicitement converti en pointeur vers **Type**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// auto_ptr_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
void function ( auto_ptr<Int> &pi )  
{  
   ++( *pi );  
   auto_ptr<Int> pi2( pi );  
   ++( *pi2 );  
   pi = pi2;  
}  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   cout << pi->x << endl;  
   function( pi );  
   cout << pi->x << endl;  
}  
```  
  
```Output  
Constructing 00311AF8  
5  
7  
Destructing 00311AF8  
```  
  
##  <a name="a-nameautoptrelementtypea--autoptrelementtype"></a><a name="auto_ptr__element_type"></a>  auto_ptr::element_type  
 Le type est un synonyme du paramètre de modèle **Type**.  
  
```  
 
typedef Type element  _type;  
```  
  
##  <a name="a-nameautoptrgeta--autoptrget"></a><a name="auto_ptr__get"></a>  auto_ptr::get  
 La fonction membre retourne le pointeur stocké **myptr**.  
  
```   
Type *get() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur stocké **myptr**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// auto_ptr_get.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      x = i;  
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;   
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;   
   };  
  
   int x;  
  
};  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   pi.reset( new Int( 6 ) );  
   Int* pi2 = pi.get ( );  
   Int* pi3 = pi.release ( );  
   if (pi2 == pi3)  
      cout << "pi2 == pi3" << endl;  
   delete pi3;  
}  
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="a-nameautoptroperatoreqa--autoptroperator"></a><a name="auto_ptr__operator_eq"></a>  auto_ptr::operator=  
 Opérateur d'assignation qui transfère la propriété d'un objet `auto_ptr` à un autre.  
  
```  
template <class Other>  
auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Objet de type `auto_ptr`.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à un objet de type `auto_ptr`\< **Type**.  
  
### <a name="remarks"></a>Notes  
 L’assignation évalue l’expression **delete myptr**, mais uniquement si le pointeur stocké **myptr** est modifié suite à l’assignation. Elle transfère ensuite la propriété du pointeur stocké dans _ *Right* en stockant \_ *Right*. [release](#auto_ptr__release) dans **myptr**. La fonction retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation de l’opérateur membre, consultez [auto_ptr::auto_ptr](#auto_ptr__auto_ptr).  
  
##  <a name="a-nameautoptroperatorstara--autoptroperator"></a><a name="auto_ptr__operator_star"></a>  auto_ptr::operator*  
 Opérateur de déréférencement pour les objets de type `auto_ptr`.  
  
```   
Type& operator*() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à un objet de type **Type** dont le pointeur est propriétaire.  
  
### <a name="remarks"></a>Notes  
 L’opérateur d’indirection retourne `*`[get](#auto_ptr__get). Par conséquent, le pointeur stocké ne doit pas être null.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation de la fonction membre, consultez [auto_ptr::auto_ptr](#auto_ptr__auto_ptr).  
  
##  <a name="a-nameautoptroperator-gta--autoptroperator-gt"></a><a name="auto_ptr__operator-_gt_"></a>  auto_ptr::operator-&gt;  
 Opérateur pour autoriser l'accès aux membres.  
  
```   
Type * operator->() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Membre de l’objet dont **auto_ptr** est propriétaire.  
  
### <a name="remarks"></a>Notes  
 L’opérateur de sélection retourne [get](#auto_ptr__get)`( )` de sorte que l’expression *ap*-> **member** se comporte comme (*ap*. **get**( ) )-> **member**, où *ap* est un objet de classe `auto_ptr`\< **Type**>. Par conséquent, le pointeur stocké ne doit pas être null et **Type** doit être une classe, un struct ou un type d’union avec un membre **member**.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation de la fonction membre, consultez [auto_ptr::auto_ptr](#auto_ptr__auto_ptr).  
  
##  <a name="a-nameautoptroperatorautoptrltothergta--autoptroperator-autoptrltothergt"></a><a name="auto_ptr__operator_auto_ptr_lt_other_gt_"></a>  auto_ptr::operator auto_ptr&lt;Other&gt;  
 Effectue un cast d'un type de `auto_ptr` vers un autre type de `auto_ptr`.  
  
```   
template <class Other>  
operator auto _ptr<Other>() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’opérateur de cast de type retourne `auto_ptr` \< **Other**>(**\*this**).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// auto_ptr_op_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
int main()  
{  
   auto_ptr<int> pi ( new int( 5 ) );  
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;  
}  
```  
  
##  <a name="a-nameautoptroperatorautoptrrefltothergta--autoptroperator-autoptrrefltothergt"></a><a name="auto_ptr__operator_auto_ptr_ref_lt_other_gt_"></a>  auto_ptr::operator auto_ptr_ref&lt;Other&gt;  
 Effectue un cast d’un `auto_ptr` en un **auto_ptr_ref**.  
  
```   
template <class Other>  
operator auto _ptr  _ref<Other>() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’opérateur de cast de type retourne **auto_ptr_ref**\< **Other**>(**\*this**).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// auto_ptr_op_auto_ptr_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer  
    // f(ciap);   
    f(iap); // compiles, but gives up ownership of pointer  

            // here, iap owns a destroyed pointer so the following is bad:  
            // *iap = 5; // BOOM  

    cout << "main exiting\n";
}
```  
  
```Output  
~C:  2  
main exiting  
~C:  1  
```  
  
##  <a name="a-nameautoptrreleasea--autoptrrelease"></a><a name="auto_ptr__release"></a>  auto_ptr::release  
 Le membre remplace le pointeur stocké **myptr** par un pointeur null et retourne le pointeur stocké précédemment.  
  
```   
Type *release() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur stocké précédemment.  
  
### <a name="remarks"></a>Notes  
 Le membre remplace le pointeur stocké **myptr** par un pointeur null et retourne le pointeur stocké précédemment.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// auto_ptr_release.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="a-nameautoptrreseta--autoptrreset"></a><a name="auto_ptr__reset"></a>  auto_ptr::reset  
 La fonction membre évalue l’expression **delete**Â **myptr**, mais uniquement si la valeur du pointeur stocké **myptr** est modifiée suite à un appel de fonction. Elle remplace ensuite le pointeur stocké par **ptr**.  
  
```   
void reset(Type* ptr = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 ` ptr`  
 Pointeur spécifié pour remplacer le pointeur stocké **myptr**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// auto_ptr_reset.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique_ptr, classe](../standard-library/unique-ptr-class.md)


