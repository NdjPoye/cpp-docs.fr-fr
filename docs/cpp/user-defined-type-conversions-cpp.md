---
title: "Conversions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "explicit_cpp"
  - "explicit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrainte"
  - "constructeurs [C++], et constantes"
  - "constructeurs [C++], conversion"
  - "constructeurs [C++], inconvénients"
  - "constructeurs de conversion"
  - "fonctions de conversion"
  - "fonctions de conversion, règles de déclaration"
  - "conversions (C++), par des constructeurs"
  - "conversions (C++), explicites"
  - "convertir des objets"
  - "conversion de type de données (C++), explicites"
  - "déclarer des fonctions, fonctions de conversion"
  - "explicit (mot clé)"
  - "fonctions (C++), conversion"
  - "objets (C++), convertir"
  - "conversion de type"
  - "conversion de type (C++), conversion explicite"
ms.assetid: d40e4310-a190-4e95-a34c-22c5c20aa0b9
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conversions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une *conversion* produit une nouvelle valeur d'un type donné à partir d'une valeur d'un autre type.  Les *conversions standard* sont générées en langage C\+\+ et prennent en charge ses types intégrés. Vous pouvez créer des *conversions définies par l'utilisateur* pour effectuer des conversions vers, à partir de ou entre des types définis par l'utilisateur.  
  
 Les conversions standard effectuent des conversions entre des types intégrés, entre des pointeurs ou références vers des types apparentés par héritage, vers et à partir de pointeurs void, et vers le pointeur null.  Pour plus d'informations, consultez [Conversions standard](../cpp/standard-conversions.md).  Les conversions définies par l'utilisateur effectuent des conversions entre des types définis par l'utilisateur ou entre des types définis par l'utilisateur et des types intégrés.  Vous pouvez les implémenter en tant que [Constructeurs de conversion](#ConvCTOR) ou [Fonctions de conversion](#ConvFunc).  
  
 Les conversions peuvent être explicites \(quand le programmeur appelle un type pour qu'il soit converti en un autre type, comme dans une diffusion ou une initialisation directe\) ou implicites \(quand le langage ou le programme appelle un autre type que celui qui a été donné par le programmeur\).  
  
 Les conversions implicites sont tentées dans les conditions suivantes :  
  
-   un argument fourni à une fonction n'est pas du même type que le paramètre correspondant ;  
  
-   la valeur retournée d'une fonction n'est pas du même type que le type de retour de la fonction ;  
  
-   une expression d'initialiseur n'est pas du même type que l'objet qu'elle initialise ;  
  
-   une expression qui contrôle une instruction conditionnelle, une construction de boucles ou un commutateur n'est pas du type requis pour exercer ce contrôle.  
  
-   un opérande fourni à un opérateur n'est pas du même type que le paramètre d'opérande correspondant.  Pour les opérateurs intégrés, les deux opérandes doivent être du même type et sont convertis en un type commun qui représente les deux.  Pour plus d'informations, consultez [Conversions arithmétiques](../misc/arithmetic-conversions.md).  Pour les opérateurs définis par l'utilisateur, chaque opérande doit être du même type que le paramètre d'opérande correspondant.  
  
 Quand une conversion standard ne peut pas terminer une conversion implicite, le compilateur peut utiliser une conversion définie par l'utilisateur, suivie éventuellement d'une autre conversion standard, pour la terminer.  
  
 Quand plusieurs conversions définies par l'utilisateur effectuant la même conversion sont disponibles sur un site de conversion, la conversion est dite ambiguë.  Ces ambiguïtés sont une erreur, car le compilateur ne peut pas déterminer quelle conversion choisir parmi les conversions disponibles.  Toutefois, ce n'est pas une erreur de définir plusieurs façons d'effectuer la même conversion, car l'ensemble des conversions disponibles peut être différent selon l'emplacement où elles se trouvent dans le code source \(par exemple, en fonction des fichiers d'en\-tête inclus dans un fichier source\).  Si une seule conversion est disponible sur le site de conversion, il n'y a pas d'ambiguïté.  Il existe plusieurs raisons aux conversions ambiguës, mais les plus courantes sont les suivantes :  
  
-   Héritage multiple.  La conversion est définie dans plusieurs classes de base.  Pour plus d'informations, consultez [\(NOTINBUILD\) Ambiguity](http://msdn.microsoft.com/fr-fr/0b399cab-40a7-4e79-9278-05f40139a0e1).  
  
-   Appel de fonction ambigu.  La conversion est définie en tant que constructeur de conversion du type cible et en tant que fonction de conversion du type source.  Pour plus d'informations, consultez [Fonctions de conversion](#ConvFunc).  
  
 Vous pouvez généralement résoudre une ambiguïté en qualifiant le nom du type impliqué de manière plus complète ou en effectuant une diffusion explicite pour clarifier votre intention.  
  
 Les constructeurs de conversion et les fonctions de conversion sont régis par des règles de contrôle d'accès par membre, mais l'accessibilité des conversions n'est possible que si et quand une conversion n'est pas considérée comme ambiguë.  Cela signifie qu'une conversion peut être ambiguë même si le niveau d'accès d'une conversion concurrente l'empêche d'être utilisée.  Pour plus d'informations sur l'accessibilité des membres, voir [Contrôle d'accès aux membres](../cpp/member-access-control-cpp.md).  
  
## Le mots clé explicite et les problèmes liés à la conversion implicite  
 Par défaut, quand vous créez une conversion définie par l'utilisateur, le compilateur peut l'utiliser pour effectuer des conversions implicites.  Parfois, c'est ce que vous voulez, mais parfois, les règles simples qui guident le compilateur dans la création de conversions implicites peut l'amener à accepter du code qu'il ne devrait pas.  
  
 Un exemple bien connu de conversion implicite pouvant engendrer des problèmes est la conversion en `bool`.  Plusieurs raisons peuvent vous motiver à créer un type de classe pouvant être utilisé dans un contexte booléen \(par exemple, pour contrôler une instruction `if` ou une boucle\) mais quand le compilateur effectue une conversion définie par l'utilisateur vers un type intégré, il est autorisé à appliquer ensuite une conversion standard supplémentaire.  Le but de cette conversion standard supplémentaire est d'autoriser des actions comme la promotion de `short` en `int`, mais elle permet aussi des conversions moins évidentes \(par exemple, de `bool` en `int`, ce qui permet à votre type de classe d'être utilisé dans des contextes d'entiers que vous n'aviez pas envisagés.  Ce problème particulier est connu comme le *problème Safe Bool*.  C'est pour ce type de problème que le mot clé `explicit` peut être utile.  
  
 Le mot clé `explicit` indique au compilateur que la conversion spécifiée ne peut pas être utilisée pour effectuer des conversions implicites.  Avant l'introduction du mot clé `explicit`, si vous vouliez la commodité syntaxique des conversions implicites, vous deviez accepter les conséquences involontaires engendrées parfois par la conversion implicite ou utiliser à la place des fonctions de conversion nommée moins pratiques.  Maintenant, grâce au mot clé `explicit`, vous pouvez créer des conversions pratiques qui peuvent être utilisées uniquement pour effectuer des diffusions explicites ou une initialisation directe, et qui n'entraîneront pas le type de problème illustré par le problème Safe Bool.  
  
 Le mot clé `explicit` peut être appliqué aux constructeurs de conversion depuis C\+\+98 et aux fonctions de conversion depuis C\+\+11.  Les sections suivantes contiennent plus d'informations sur la façon d'utiliser le mot clé `explicit`.  
  
##  <a name="ConvCTOR"></a> Constructeurs de conversion  
 Les constructeurs de conversion définissent les conversions de types définis par l'utilisateur ou intégrés en type défini par l'utilisateur.  L'exemple suivant décrit un constructeur de conversion convertissant le type intégré `double` en type `Money` défini par l'utilisateur.  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    Money(double _amount) : amount{ _amount } {};  
  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << balance.amount << std::endl;  
}  
  
int main(int argc, char* argv[])  
{  
    Money payable{ 79.99 };  
  
    display_balance(payable);  
    display_balance(49.95);  
    display_balance(9.99f);  
  
    return 0;  
}  
```  
  
 Notez que le premier appel de la fonction `display_balance`, qui prend un argument de type `Money`, ne requiert aucune conversion, car le type de son argument est correct.  Toutefois, sur le deuxième appel de `display_balance`, une conversion est nécessaire, car le type de l'argument, un `double` avec une valeur de `49,95`, n'est pas celui attendu par la fonction.  La fonction ne peut pas utiliser cette valeur directement, mais par conversion du type de l'argument \(`double`\) en type du paramètre correspondant \(`Money`\), une valeur temporaire du type `Money` est construite à partir de l'argument et utilisée pour terminer l'appel de la fonction.  Dans le troisième appel de `display_balance`, notez que l'argument n'est pas un `double` mais un `float` avec une valeur de `9,99`. Pourtant l'appel de la fonction peut encore être terminé, car le compilateur peut effectuer une conversion standard \(dans ce cas, de `float` en `double`\), puis effectuer la conversion définie par l'utilisateur de `double` en `Money` pour terminer la conversion nécessaire.  
  
### Déclaration des constructeurs de conversion  
 Les règles suivantes s'appliquent à la déclaration d'un constructeur de conversion :  
  
-   Le type cible de la conversion est le type défini par l'utilisateur en cours de construction.  
  
-   Les constructeurs de conversion prennent généralement un seul argument, qui est de type source.  Toutefois, un constructeur de conversion peut spécifier d'autres paramètres si chaque paramètre supplémentaire a une valeur par défaut.  Le type source reste le type du premier paramètre.  
  
-   Les constructeurs de conversion, comme tous les constructeurs, ne spécifient pas de type de retour.  La spécification d'un type de retour dans la déclaration constitue une erreur.  
  
-   Les constructeurs de conversion peuvent être explicites.  
  
### Constructeurs de conversion explicites  
 En déclarant qu'un constructeur de conversion doit être `explicit`, il ne peut être utilisé que pour effectuer une initialisation directe d'un objet ou un transtypage explicite.  Cela empêche les fonctions acceptant un argument du type de la classe d'accepter également de manière implicite des arguments du type source du constructeur de conversion, et empêche le type de la classe d'être initialisé par copie d'une valeur du type source.  L'exemple suivant décrit comment définir un constructeur de conversion explicite et son impact sur le code formé correctement.  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    explicit Money(double _amount) : amount{ _amount } {};  
  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << balance.amount << std::endl;  
}  
  
int main(int argc, char* argv[])  
{  
    Money payable{ 79.99 };        // Legal: direct initialization is explicit.  
  
    display_balance(payable);      // Legal: no conversion required  
    display_balance(49.95);        // Error: no suitable conversion exists to convert from double to Money.  
    display_balance((Money)9.99f); // Legal: explicit cast to Money  
  
    return 0;  
}  
```  
  
 Dans cet exemple, notez que vous pouvez encore utiliser le constructeur de conversion explicite pour effectuer une initialisation directe de `payable`.  Si au lieu de cela vous devez initialiser par copie `Money payable = 79.99;`, cela constituerait une erreur.  Le premier appel de `display_balance` n'est pas affecté, car l'argument est de type correct.  Le deuxième appel de `display_balance` constitue une erreur, car le constructeur de conversion ne peut pas être utilisé pour effectuer des conversions implicites.  Le troisième appel de `display_balance` est autorisé en raison du transtypage explicite en `Money`, mais notez que le compilateur a encore aidé à terminer le transtypage en insérant un transtypage implicite de `float` en `double`.  
  
 Même si vous pouvez être tenté par la commodité de l'autorisation des conversions implicites, celle\-ci peut introduire des bogues difficiles à trouver.  De manière générale, il vaut mieux que tous les constructeurs de conversion soient explicites, sauf quand vous êtes sûr que vous voulez qu'une conversion spécifique se produise de manière implicite.  
  
##  <a name="ConvFunc"></a> Fonctions de conversion  
 Les fonctions de conversion définissent des conversions d'un type défini par l'utilisateur en d'autres types.  Ces fonctions sont parfois qualifiées d'« opérateurs de transtypage », car elles sont appelées, en même temps que les constructeurs de conversion, quand une valeur est transtypée vers un type différent.  L'exemple suivant décrit une fonction de conversion convertissant le type `Money` défini par l'utilisateur en type intégré `double` :  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    Money(double _amount) : amount{ _amount } {};  
  
    operator double() const { return amount; }  
private:  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << balance << std::endl;  
}  
  
```  
  
 Notez que la variable membre `amount` est privée et qu'une fonction de conversion publique vers un type `double` est introduite uniquement pour retourner la valeur de `amount`.  Dans la fonction `display_balance`, une conversion implicite se produit quand la valeur de `balance` est diffusée sur la sortie standard à l'aide de l'opérateur d'insertion de flux `<<`.  Dans la mesure où aucun opérateur d'insertion de flux n'est défini pour le type `Money` défini par l'utilisateur, mais qu'il y en a un pour le type intégré `double`, le compilateur peut utiliser la fonction de conversion de `Money` en `double` pour satisfaire l'opérateur d'insertion de flux.  
  
 Les fonctions de conversion sont héritées dans les classes dérivées.  Les fonctions de conversion d'une classe dérivée ne peuvent remplacer une fonction de conversion héritée que lorsqu'elles convertissent vers le même type exactement.  Par exemple, une fonction de conversion définie par l'utilisateur de la classe dérivée `operator int` ne remplace pas \(ni influence\) une fonction de conversion définie par l'utilisateur de la classe de base `operator short`, même si les conversions standard définissent une relation de conversion entre `int` et `short`.  
  
### Déclaration des fonctions de conversion  
 Les règles suivantes s'appliquent à la déclaration d'une fonction de conversion :  
  
-   Le type cible de la conversion doit être déclaré avant la déclaration de la fonction de conversion.  Les classes, structures, énumérations et typedefs ne peuvent pas être déclarés dans la déclaration de la fonction de conversion.  
  
    ```  
    operator struct String { char string_storage; }() // illegal  
    ```  
  
-   Les fonctions de conversion ne prennent pas d'arguments.  La spécification d'un paramètre dans la déclaration constitue une erreur.  
  
-   Les fonctions de conversion ont un type de retour spécifié par le nom de la fonction de conversion, qui est également le nom du type cible de la conversion.  La spécification d'un type de retour dans la déclaration constitue une erreur.  
  
-   Les fonctions de conversion peuvent être virtuelles.  
  
-   Les fonctions de conversion peuvent être explicites.  
  
### Fonctions de conversion explicites  
 Quand une fonction de conversion est déclarée comme explicite, elle ne peut être utilisée que pour effectuer un transtypage explicite.  Cela empêche les fonctions acceptant un argument du type cible de la fonction de conversion d'accepter également de manière implicite des arguments du type de la classe, et empêche les instances du type cible d'être initialisées par copie d'une valeur du type de la classe.  L'exemple suivant décrit comment définir une fonction de conversion explicite et son impact sur le code formé correctement.  
  
```  
#include <iostream>  
  
class Money  
{  
public:  
    Money() : amount{ 0.0 } {};  
    Money(double _amount) : amount{ _amount } {};  
  
    explicit operator double() const { return amount; }  
private:  
    double amount;  
};  
  
void display_balance(const Money balance)  
{  
    std::cout << "The balance is: " << (double)balance << std::endl;  
}  
  
```  
  
 Le fonction de conversion `operator double` est explicite et un transtypage explicite vers le type `double` a été introduit dans la fonction `display_balance` pour effectuer la conversion.  Si ce transtypage est omis, le compilateur est incapable de rechercher un opérateur d'insertion de flux `<<` convenable pour le type `Money` et une erreur se produit.  
  
## Voir aussi  
 [Fonctions membres spéciales](../misc/special-member-functions-cpp.md)