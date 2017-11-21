---
title: constexpr (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: constexpr_cpp
dev_langs: C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4ff111b73d81fd3c008e53db0f5e41b82f9e3753
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="constexpr-c"></a>constexpr (C++)
Le mot clé `constexpr` a été introduit dans C++11 et amélioré dans C++14. Cela signifie que *expression constante*. Comme le mot clé `const`, il peut être appliqué aux variables pour spécifier que leur valeur n'est pas modifiable. Si du code tente de modifier la valeur, une erreur de compilation se produit. Contrairement à `const`, `constexpr` peut également être appliqué aux fonctions et aux constructeurs de classe. `constexpr` indique que la valeur ou la valeur de retour est constante et qu'elle sera calculée au moment de la compilation, si possible.  Une valeur intégrale `constexpr` peut être utilisée partout où un entier const est requis, comme dans les arguments de modèle et les déclarations de tableau. Et, lorsqu’une valeur peut être calculée au moment de la compilation au lieu de l’exécution, il peut aider votre programme de s’exécuter plus rapidement et utilisent moins de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `params`  
 Un ou plusieurs paramètres qui doivent être un type de littéral (comme indiqué ci-dessous), lui-même devant être une expression constante.  
  
## <a name="return-value"></a>Valeur de retour  
 Une variable ou fonction constexpr doit retourner l'un des types de littéral répertoriés ci-après.  
  
## <a name="literal-types"></a>Types de littéral  
 Pour faciliter le traitement des constantes au moment de la compilation et limiter leur impact potentiel sur la durée de compilation, la norme C++14 impose que les types utilisés dans les expressions constantes soient uniquement des types de littéral. Un type de littéral est un type dont la disposition peut être déterminée au moment de la compilation. Voici les types de littéral disponibles :  
  
1.  void  
  
2.  Types scalaires  
  
3.  Références  
  
4.  Tableaux de types void, de types scalaires ou de références  
  
5.  Classe contenant un destructeur trivial, et un ou plusieurs constructeurs constexpr autres que des constructeurs de copie ou de déplacement. Tous les membres de données non statiques et classes de base doivent également être des types de littéral et être non volatiles.  
  
## <a name="constexpr-variables"></a>Variables constexpr  
 La principale différence entre les variables const et constexpr est que l'initialisation d'une variable const peut être différée jusqu'à l'exécution, alors qu'une variable constexpr doit être initialisée au moment de la compilation.  Toutes les variables constexpr sont de type const.  

-  Une variable peut être déclarée avec `constexpr` si elle a un type de littéral et est initialisée. Si l'initialisation est effectuée par un constructeur, celui-ci doit également être déclaré avec `constexpr`.  
  
-   Une référence peut être déclarée avec constexpr si l'objet référencé a été initialisé par une expression constante et que toutes les conversions implicites appelées pendant l'initialisation sont aussi des expressions constantes.  
  
-   Toutes les déclarations d'une variable ou d'une fonction `constexpr` doivent comporter le spécificateur `constexpr`.  
  
 
  
 
  
```cpp  
constexpr float x = 42.0;  
constexpr float y{108};  
constexpr float z = exp(5, 3);  
constexpr int i; // Error! Not initialized  
int j = 0;  
constexpr int k = j + 1; //Error! j not a constant expression  
```  
  
## <a name="constexpr-functions"></a>Fonctions constexpr  
 Une fonction `constexpr` est une fonction dont la valeur de retour peut être calculée au moment de la compilation lorsque le code de consommation en a besoin.  Quand ses arguments sont des valeurs `constexpr` et que le code de consommation a besoin de la valeur de retour au moment de la compilation, notamment pour initialiser une variable `constexpr` ou fournir un argument de modèle sans type, la fonction génère une constante au moment de la compilation. Si ses arguments ne sont pas des valeurs `constexpr`, ou si la valeur de retour n'est pas requise au moment de la compilation, la fonction appelée génère une valeur à l'exécution comme une fonction régulière.  (Ce double comportement vous évite d'avoir à écrire deux versions, `constexpr` et non `constexpr`, de la même fonction.)  
 
 Une fonction ou un constructeur `constexpr` est implicitement `inline`. 
 
 Les règles suivantes s’appliquent aux fonctions constexpr :

- Une fonction `constexpr` doit accepter et retourner des types de littéral uniquement. 

- Une fonction `constexpr` peut être récursive, 

- Il ne peut pas être [virtuels](../cpp/virtual-cpp.md). A un constructeur ne peut pas être défini en tant que constexpr si la classe englobante contient toutes les classes de base virtuelles.

- Le corps de la fonction peut être défini avec la valeur `= default` ou `= delete`. 

- Le corps ne peut pas contenir `goto` instructions ou des blocs try. 

- Une spécialisation explicite d'un modèle non constexpr peut être déclarée avec `constexpr`:  
  
- Une spécialisation explicite d'un modèle `constexpr` ne doit pas obligatoirement être déclarée avec `constexpr`: 


<!--conformance note-->
Les règles suivantes s’appliquent aux fonctions constexpr dans Visual Studio 2017 et versions ultérieures : 

- Il peut contenir si basculer des instructions et toutes les instructions en boucle, y compris, de la plage de base, tandis qu’et faire-tandis que
    
- Il peut contenir les déclarations de variable locale, mais la variable doit être initialisée, doit être un type littéral et ne peut pas être statique ou de thread local. La variable locale déclarée n’est pas requis pour être const et peut-être se transformer en.

- Une fonction membre non static de constexpr n’est pas requis pour être implicitement const.

  
```cpp  
constexpr float exp(float x, int n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp(x * x, n / 2) :  
        exp(x * x, (n - 1) / 2) * x;  
};  
```  
  
> [!TIP]
>  Remarque : dans le débogueur Visual Studio, vous pouvez indiquer si une fonction `constexpr` est évaluée au moment de la compilation en y plaçant un point d'arrêt. Si le point d'arrêt est atteint, la fonction a été appelée à l'exécution.  Sinon, la fonction a été appelée au moment de la compilation.  
  
 
## <a name="example"></a>Exemple  
 L'exemple suivant montre des variables et des fonctions `constexpr`, ainsi qu'un type défini par l'utilisateur. Notez que, dans la dernière instruction dans main(), la fonction membre GetValue() `constexpr` est un appel d'exécution, car la valeur n'est pas requise par le code au moment de la compilation.  
  
```  
#include <iostream>  
  
using namespace std;  
  
// Pass by value   
constexpr float exp(float x, int n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp(x * x, n / 2) :  
        exp(x * x, (n - 1) / 2) * x;  
};  
  
// Pass by reference  
constexpr float exp2(const float& x, const int& n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp2(x * x, n / 2) :  
        exp2(x * x, (n - 1) / 2) * x;  
};  
  
// Compile time computation of array length  
template<typename T, int N>  
constexpr int length(const T(&ary)[N])   
{   
    return N;   
}   
  
// Recursive constexpr function  
constexpr int fac(int n)  
{   
    return n == 1 ? 1 : n*fac(n - 1);   
}  
  
// User-defined type  
class Foo  
{  
public:  
    constexpr explicit Foo(int i) : _i(i) {}  
    constexpr int GetValue()  
    {  
        return _i;  
    }  
private:  
    int _i;  
};  
  
int main()  
{  
    //foo is const:  
    constexpr Foo foo(5);   
    // foo = Foo(6); //Error!  
  
    //Compile time:  
    constexpr float x = exp(5, 3);   
    constexpr float y { exp(2, 5) };  
    constexpr int val = foo.GetValue();   
    constexpr int f5 = fac(5);  
    const int nums[] { 1, 2, 3, 4 };  
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };  
  
    //Run time:   
    cout << "The value of foo is " << foo.GetValue() << endl;   
  
}  
  
```  
  
## <a name="requirements"></a>Spécifications  
 Visual Studio 2015  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations et définitions](../cpp/declarations-and-definitions-cpp.md)   
 [const](../cpp/const-cpp.md)