---
title: Opérateur static_cast | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- static_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a0cd6ea7e2268940febca9e1e564f30d29dcff0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="staticcast-operator"></a>static_cast, opérateur
Convertit un *expression* pour le type de *id de type,* basés uniquement sur les types qui sont présents dans l’expression.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>Notes  
 Dans C++ standard, aucun contrôle de type à l'exécution n'est fait pour garantir la sécurité de la conversion. Dans C++/CX, il est procédé à un calcul du temps de compilation et à un contrôle à l'exécution. Pour plus d’informations, consultez [conversion](casting.md).  
  
 L'opérateur `static_cast` peut être utilisé pour des opérations telles que la conversion d'un pointeur vers une classe de base à un pointeur vers une classe dérivée. Ces conversions ne sont pas toujours sûres.  
  
 En général, vous utilisez `static_cast` lorsque vous souhaitez convertir des types de données numériques tels que enums en ints ou ints en floats, et que vous êtes certain des types de données impliqués dans la conversion. Les conversions `static_cast` ne sont pas aussi sûres que les conversions `dynamic_cast`, parce que `static_cast` ne fait pas de contrôle de type à l'exécution, au contraire de `dynamic_cast` . `dynamic_cast` sur un pointeur ambigu échoue, tandis que `static_cast` retourne comme si rien n'était erroné ; cela peut être dangereux. Bien que les conversions de `dynamic_cast` soient plus sûres, `dynamic_cast` fonctionne uniquement sur des pointeurs ou des références, et le contrôle du type à l'exécution est une charge mémoire. Pour plus d’informations, consultez [opérateur dynamic_cast](../cpp/dynamic-cast-operator.md).  
  
 Dans l'exemple qui suit, la ligne `D* pd2 = static_cast<D*>(pb);` n'est pas sécurisée car `D` peut avoir des champs et des méthodes qui ne sont pas dans `B`. Toutefois, la ligne `B* pb2 = static_cast<B*>(pd);` est une conversion sûre car `D` contient toujours tout le `B`.  
  
```  
// static_cast_Operator.cpp  
// compile with: /LD  
class B {};  
  
class D : public B {};  
  
void f(B* pb, D* pd) {  
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields  
                                   // and methods that are not in B.  
  
   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always  
                                   // contains all of B.  
}  
```  
  
 Contrairement à [dynamic_cast](../cpp/dynamic-cast-operator.md), aucune vérification de l’exécution est effectuée sur le `static_cast` conversion de `pb`. L'objet pointé par `pb` peut ne pas être un objet de type `D`, auquel cas l'utilisation de `*pd2` peut être désastreuse. Par exemple, appeler une fonction membre de la classe `D`, mais pas de la classe `B`, peut entraîner une violation d'accès.  
  
 Les opérateurs `dynamic_cast` et `static_cast` déplacent un pointeur à travers une hiérarchie de classes. Toutefois, `static_cast` s'appuie exclusivement sur les informations fournies dans l'instruction de lancement et peut donc être potentiellement dangereux. Par exemple :  
  
```  
// static_cast_Operator_2.cpp  
// compile with: /LD /GR  
class B {  
public:  
   virtual void Test(){}  
};  
class D : public B {};  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  
   D* pd2 = static_cast<D*>(pb);  
}  
```  
  
 Si `pb` pointe vraiment sur un objet de type `D`, alors `pd1` et `pd2` reçoivent la même valeur. Ils auront également la même valeur si `pb == 0`.  
  
 Si `pb` pointe sur un objet de type `B` et non sur la classe `D`, alors `dynamic_cast` en connaîtra suffisamment pour retourner zéro. Toutefois, `static_cast` repose sur l'assertion du programmeur que `pb` pointe sur un objet de type `D` et retourne simplement un pointeur vers cet objet supposé `D`.  
  
 Par conséquent, `static_cast` peut faire l'inverse de conversions implicites, auquel cas les résultats sont indéfinis. Il est laissé au programmeur le soin de vérifier que les résultats d'une conversion `static_cast` sont sécurisés.  
  
 Ce comportement s'applique également aux types autres que les types de classe. Par exemple, `static_cast` peut être utilisé pour convertir un entier en `char`. Toutefois, le `char` résultant peut ne pas avoir suffisamment de bits pour conserver toute la valeur de `int`. Là encore, il est laissé au programmeur pour vérifier que les résultats d’une `static_cast` conversion sont sécurisés.  
  
 L'opérateur `static_cast` peut également être utilisé pour exécuter toute conversion implicite, notamment les conversions standard et les conversions définies par l'utilisateur. Par exemple :  
  
```  
// static_cast_Operator_3.cpp  
// compile with: /LD /GR  
typedef unsigned char BYTE;  
  
void f() {  
   char ch;  
   int i = 65;  
   float f = 2.5;  
   double dbl;  
  
   ch = static_cast<char>(i);   // int to char  
   dbl = static_cast<double>(f);   // float to double  
   i = static_cast<BYTE>(ch);  
}  
```  
  
 L'opérateur `static_cast` peut convertir explicitement une valeur entière en un type d'énumération. Si la valeur du type entier ne fait pas partie de la plage des valeurs d'énumération, la valeur d'énumération résultante n'est pas définie.  
  
 L'opérateur `static_cast` convertit une valeur de pointeur null en la valeur de pointeur null du type de destination.  
  
 Toute expression peut être explicitement convertie en type vide par l'opérateur `static_cast`. Le type vide de destination peut éventuellement inclure les attributs `const`, `volatile`, ou `__unaligned`.  
  
 L'opérateur `static_cast` ne peut pas rejeter les attributs `const`, `volatile`, ou `__unaligned`. Consultez [opérateur const_cast](../cpp/const-cast-operator.md) pour plus d’informations sur la suppression de ces attributs.  
  
 En raison du risque d'effectuer des rejets non vérifiés en plus d'une relocation dans le récupérateur de mémoire, l'utilisation de `static_cast` ne doit être présente dans un code critique que lorsque vous êtes certain qu'il fonctionne correctement. Si vous devez utiliser `static_cast` en mode version finale, remplacez-le par ce avec [safe_cast](../windows/safe-cast-cpp-component-extensions.md) dans vos versions debug pour garantir la réussite.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs de casting](../cpp/casting-operators.md)   
 [Mots clés](../cpp/keywords-cpp.md)