---
title: "Extensions Microsoft pour&#160;C et&#160;C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! d'opérateur, extensions pour C++"
  - "!= (opérateur)"
  - "& (opérateur), extensions pour C/C++"
  - "&& (opérateur)"
  - "&= (opérateur)"
  - "^ (opérateur), extensions pour C/C++"
  - "^= (opérateur), extensions pour C++"
  - "| (opérateur), extensions"
  - "|| (opérateur)"
  - "|= (opérateur)"
  - "~ (opérateur), extensions pour C/C++"
  - "And (opérateur), extensions pour C/C++"
  - "and_eq (opérateur)"
  - "compl (méthode)"
  - "extensions"
  - "extensions, langage C"
  - "iso646.h (en-tête)"
  - "extensions Microsoft pour C et C++"
  - "NOT (opérateur)"
  - "not_eq (opérateur)"
  - "Or (opérateur), extensions Microsoft pour C et C++"
  - "or_eq (opérateur)"
  - "Visual C, extensions Microsoft"
  - "Visual C++, extensions pour C/C++"
  - "Xor (opérateur), extensions Microsoft pour C et C++"
  - "xor_eq (opérateur)"
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Extensions Microsoft pour&#160;C et&#160;C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ étend les normes ANSI C et ANSI C\+\+ comme suit.  
  
## Mots clés  
 Plusieurs mots clés sont ajoutés.  Dans la liste dans [Mots clés C\+\+](../../cpp/keywords-cpp.md), les mots clés qui ont deux principaux traits de soulignement sont des extensions Visual C\+\+.  
  
## Définition hors classe des membres static, const, integral \(ou enum\)  
 Dans le standard \(**\/Za**\), vous devez absolument créer une définition hors classe pour les membres de données.  
  
```  
class CMyClass  {  
   static const int max = 5;  
   int m_array[max];  
}  
...  
const int CMyClass::max;   // out of class definition  
```  
  
 Sous **\/Ze**, la définition hors classe est facultative pour les données membres static, const integral et const enum.  Seuls les membres intégraux et enum qui sont de type static et const peuvent avoir des initialiseurs dans une classe ; l'expression d'initialisation doit être une expression de type const.  
  
 Pour éviter les erreurs lorsqu'une définition hors classe est fournie dans un fichier d'en\-tête et que le fichier d'en\-tête est inclus dans plusieurs fichiers sources, utilisez [selectany](../../cpp/selectany.md).  Par exemple :  
  
```  
__declspec(selectany) const int CMyClass::max = 5;  
```  
  
## Casts  
 Le compilateur C\+\+ et le compilateur C prennent tous les deux en charge ces types de casts non ANSI :  
  
-   Utilisation de casts non\-ANSI pour produire des l\-values.  Par exemple :  
  
    ```  
    char *p;  
    (( int * ) p )++;  
    ```  
  
    > [!NOTE]
    >  Cette extension est disponible uniquement dans le langage C.  Utilisez le formulaire de norme C ANSI suivant dans du code C\+\+ pour modifier un pointeur comme s'il est un pointeur vers un autre type.  
  
     L'exemple précédent pourrait être réécrit pour être conforme avec la norme C ANSI, de la manière suivante :  
  
    ```  
    p = ( char * )(( int * )p + 1 );  
    ```  
  
-   Utilisation de casts non\-ANSI d'un pointeur fonction vers un pointeur donné.  Par exemple :  
  
    ```  
    int ( * pfunc ) ();   
    int *pdata;  
    pdata = ( int * ) pfunc;  
    ```  
  
     Pour effectuer le même cast tout en conservant la compatibilité ANSI, opérez un cast du pointeur de la fonction vers un `uintptr_t` avant d'opérer un cast de ce dernier vers un pointeur de données:  
  
    ```  
    pdata = ( int * ) (uintptr_t) pfunc;  
    ```  
  
## Listes d'arguments de longueur variable  
 Les compilateurs C et C\+\+ prennent tous les deux en charge l'utilisation d'un déclarateur de fonction qui spécifie un nombre variable d'arguments, suivi d'une définition de fonction qui fournit un type à la place :  
  
```  
void myfunc( int x, ... );  
void myfunc( int x, char * c )  
{ }  
```  
  
## Commentaires sur une seule ligne  
 Le compilateur C prend en charge sur une seule ligne les commentaires qui commencent par deux barres obliques \(\/\/\) :  
  
```  
// This is a single-line comment.  
```  
  
## Portée  
 Le compilateur C prend en charge les fonctionnalités suivantes liées à la portée.  
  
-   Redéfinitions des éléments externes \(externe\) en tant qu'éléments statiques \(static\) :  
  
    ```  
    extern int clip();  
    static int clip()  
    {}  
    ```  
  
-   Utilisation de redéfinitions typedef bénignes dans la même portée :  
  
    ```  
    typedef int INT;  
    typedef int INT;  
    ```  
  
-   Déclarateurs de fonction avec une portée de fichier :  
  
    ```  
    void func1()  
    {  
        extern int func2( double );  
    }  
    int main( void )  
    {  
        func2( 4 );    //  /Ze passes 4 as type double  
    }                  //  /Za passes 4 as type int  
    ```  
  
-   Utilisation des variables de portée de bloc qui sont initialisées à l'aide de expressions non constantes :  
  
    ```  
    int clip( int );  
    int bar( int );  
    int main( void )  
    {  
        int array[2] = { clip( 2 ), bar( 4 ) };  
    }  
    int clip( int x )  
    {  
        return x;  
    }  
    int bar( int x )  
    {  
        return x;  
    }  
    ```  
  
## Définitions et déclarations de données  
 Le compilateur C prend en charge les fonctionnalités de définition et de déclaration de données suivantes.  
  
-   Combinaison de constantes de types caractère et chaîne dans un initialiseur :  
  
    ```  
    char arr[5] = {'a', 'b', "cde"};  
    ```  
  
-   Champs de bits qui ont des types de base autres que **unsigned int** ou **signed int**.  
  
-   Déclarateurs qui n'ont pas de type :  
  
    ```  
    x;  
    int main( void )  
    {  
        x = 1;  
    }  
    ```  
  
-   Tableaux non dimensionnés comme dernier champ dans les structures et les unions :  
  
    ```  
    struct zero  
    {  
        char *c;  
        int zarray[];  
    };  
    ```  
  
-   Structures sans nom \(anonymes\) :  
  
    ```  
    struct  
    {  
        int i;  
        char *s;  
    };  
    ```  
  
-   Unions sans nom \(anonymes\) :  
  
    ```  
    union  
    {  
        int i;  
        float fl;  
    };  
    ```  
  
-   Membres sans nom :  
  
    ```  
    struct s  
    {  
       unsigned int flag : 1;  
       unsigned int : 31;  
    }  
    ```  
  
## Fonctions intrinsèques en virgule flottante  
 Les compilateurs prennent en charge tous les deux la génération incluse **x86 Specific \>** des fonctions `atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt`, et `tan` **END x86 Specific** lorsque **\/Oi** est spécifié.  Pour le compilateur C, la conformité ANSI n'est plus assurée quand ces fonctions intrinsèques sont utilisées, car elles ne définissent pas la variable `errno`.  
  
## Passage d'un paramètre pointeur non const à une fonction qui attend une référence à un paramètre pointeur const  
 Il s'agit d'une extension C\+\+.  Ce code sera compilé avec **\/Ze**:  
  
```  
typedef   int   T;  
  
const T  acT = 9;      // A constant of type 'T'  
const T* pcT = &acT;   // A pointer to a constant of type 'T'  
  
void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'  
{  
   rpcT = pcT;  
}  
  
T*   pT;               // A pointer to a 'T'  
  
void func ()  
{  
   func2 ( pT );      // Should be an error, but isn't detected  
   *pT   = 7;         // Invalidly overwrites the constant 'acT'  
}  
```  
  
## ISO646.H n'est pas activé  
 Sous **\/Ze**, vous devez inclure iso646.h si vous voulez utiliser les opérateurs suivants dans leur format texte :  
  
-   && \(et\)  
  
-   &\= \(et\_eq\)  
  
-   & \(bitand\)  
  
-   &#124; \(bitor\)  
  
-   ~ \(compl\)  
  
-   \! \(not\)  
  
-   \!\= \(not\_eq\)  
  
-   &#124;&#124; \(or\)  
  
-   &#124;\= \(or\_eq\)  
  
-   ^ \(xor\)  
  
-   ^\= \(xor\_eq\)  
  
## L'adresse du littéral de chaîne est de type const char \[\], et non const char \(\*\) \[\]  
 L'exemple suivant émet char const \(\*\)\[4\] sous **\/Za**, mais char const \[4\] sous **\/Ze**.  
  
```  
#include <stdio.h>  
#include <typeinfo>  
  
int main()  
{  
    printf_s("%s\n", typeid(&"abc").name());  
}  
```  
  
## Voir aussi  
 [\/Za, \/Ze \(Désactiver les extensions de langage\)](../../build/reference/za-ze-disable-language-extensions.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)