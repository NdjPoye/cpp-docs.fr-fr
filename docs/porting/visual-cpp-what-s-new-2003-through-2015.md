---
title: "Nouveautés de Visual C++ entre 2003 et 2015 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 512665a243a0c24c143242084a51f6b3025c1a19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Nouveautés de Visual C++ entre 2003 et 2015

**Remarque** Pour plus d’informations sur Visual Studio 2017, consultez [Nouveautés de Visual C++ dans Visual Studio 2017](../what-s-new-for-visual-cpp-in-visual-studio.md) et [Améliorations de la conformité de Visual C++ dans Visual Studio 2017](../cpp-conformance-improvements-2017.md).

Dans Visual C++ 2015 et versions ultérieures, les améliorations suivies de la conformité du compilateur peuvent parfois modifier la façon dont le compilateur comprend votre code source existant. Dans ce cas, vous pouvez être confronté à des erreurs nouvelles ou différentes pendant la génération, ou même à des différences de comportement dans le code qui auparavant était généré et paraissait s’exécuter correctement.  
  
 Heureusement, ces différences n’ont que peu ou pas d’impact sur la plus grande partie de votre code source et, quand le code source ou d’autres modifications sont nécessaires pour résoudre ces différences, les corrections sont généralement mineures et simples. Nous avons inclus de nombreux exemples de code source précédemment acceptable qui devront peut-être être changés *(avant)* et les corrections pour les modifier *(après)*.  
  
 Même si ces différences peuvent affecter votre code source ou d’autres artefacts de build, elles n’affectent pas la compatibilité binaire entre les mises à jour des versions de Visual C++. Type plus sérieux de modification, la *modification avec rupture* peut affecter la compatibilité binaire, mais ces types d’incompatibilités binaires se produisent uniquement entre les versions principales de Visual C++, par exemple entre Visual C++ 2013 et Visual C++ 2015. Pour plus d’informations sur les modifications avec rupture qui se sont produites entre Visual C++ 2013 et Visual C++ 2015, consultez [Historique des modifications de Visual C++ entre 2003 et 2015](../porting/visual-cpp-change-history-2003-2015.md).  
  
-   [Améliorations de la conformité dans Visual C++ 2015](#VS_RTM)  
  
-   [Améliorations de la conformité dans Update 1](#VS_Update1)  
  
-   [Améliorations de la conformité dans Update 2](#VS_Update2)  
  
-   [Améliorations de la conformité dans Update 3](#VS_Update3)  
  
##  <a name="VS_RTM"></a> Améliorations de la conformité dans Visual C++ 2015  
  
-   /Zc:forScope-  
  
     Options du compilateur **/Zc:forScope-** est déconseillée et sera supprimée dans une version ultérieure.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Cette option était généralement utilisée pour autoriser du code non standard utilisant des variables de boucle après le point où, selon la norme, elles devraient être hors de portée. Elle était nécessaire uniquement en cas de compilation avec l'option /Za, étant donné que sans /Za, l'utilisation d'une variable de boucle for après la fin de la boucle est toujours autorisée. Si vous ne vous souciez pas de la conformité aux normes (par exemple, si votre code n'est pas destiné à d'autres compilateurs), vous pouvez éventuellement désactiver l'option /Za (ou affecter à la propriété Désactivation des extensions de langage la valeur Non). Si vous souhaitez écrire un code portable, conforme aux normes, vous devez réécrire votre code afin qu'il soit conforme à la norme en déplaçant la déclaration de ces variables vers un point extérieur à la boucle.  
  
    ```  
    // zc_forScope.cpp  
    // compile with: /Zc:forScope- /Za  
    // C2065 expected  
    int main() {  
       // Uncomment the following line to resolve.  
       // int i;  
       for (int i =0; i < 1; i++)  
          ;  
       i = 20;   // i has already gone out of scope under /Za  
    }  
    ```  
  
-   **Option de compilateur /Zg**  
  
     L'option de compilateur /Zg (Générer des prototypes de fonction) n'est plus disponible. Cette option de compilateur a été déconseillée précédemment.  
  
-   Vous ne pouvez plus exécuter de tests unitaires avec C++/CLI à partir de la ligne de commande avec mstest.exe. À la place, utilisez vstest.console.exe. Consultez [Options de ligne de commande VSTest.Console.exe](/devops-test-docs/test/vstest-console-exe-command-line-options).  
  
-   **Mot clé mutable**  
  
     Le spécificateur de classe de stockage `mutable` n'est plus autorisé dans les emplacements où il pouvait être compilé sans erreur auparavant. À présent, le compilateur attribue l'erreur C2071 (classe de stockage non conforme). Conformément à la norme, le spécificateur mutable peut être appliqué uniquement à des noms de données membres de classe. Il ne peut pas être appliqué à des noms déclarés const ou static, ni à des membres de référence.  
  
     Considérons par exemple le code suivant :  
  
    ```  
    struct S {  
        mutable int &r;  
    };  
    ```  
  
     Les versions précédentes du compilateur Visual C++ acceptaient cela, mais le compilateur attribue désormais l'erreur suivante :  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     Pour corriger cette erreur, supprimez simplement le mot clé mutable redondant.  
  
-   **char_16_t et char32_t**  
  
     Vous ne pouvez plus utiliser `char16_t` ou `char32_t` comme alias dans un typedef, car ces types sont maintenant traités comme des types intégrés. Il était courant que des utilisateurs et des auteurs de bibliothèques définissent char16_t et char32_t en tant qu'alias de uint16_t et uint32_t, respectivement.  
  
    ```  
    #include <cstdint>  
  
    typedef uint16_t char16_t; //C2628  
    typedef uint32_t char32_t; //C2628  
  
    int main(int argc, char* argv[])  
    {  
    uint16_t x = 1; uint32_t y = 2;  
    char16_t a = x;   
    char32_t b = y;   
    return 0;  
    }  
    ```  
  
     Pour mettre à jour votre code, supprimez les déclarations typedef et renommez les autres identificateurs qui entrent en conflit avec ces noms.  
  
-   **Paramètres de modèle sans type**  
  
     Du code qui implique des paramètres de modèle sans type fait à présent l'objet d'une vérification correcte de la compatibilité des types quand vous fournissez des arguments template explicites. Par exemple, le code suivant pouvait être compilé sans erreur dans les versions antérieures de Visual C++.  
  
    ```  
    struct S1  
    {  
    void f(int);  
    void f(int, int);  
    };  
  
    struct S2  
    {  
    template <class C, void (C::*Function)(int) const> void f() {}  
    };  
  
    void f()  
    {  
    S2 s2;  
    s2.f<S1, &S1::f>();  
    }  
  
    ```  
  
     Le compilateur actuel attribue normalement une erreur, car le type de paramètre de modèle ne correspond pas à l'argument template (le paramètre est un pointeur vers un membre const, mais la fonction f est non const) :  
  
    ```Output  
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'  
    ```  
  
     Pour résoudre cette erreur dans votre code, assurez-vous que le type de l’argument template que vous utilisez correspond au type déclaré du paramètre de modèle.  
  
-   **__declspec(align)**  
  
     Le compilateur n'accepte plus `__declspec(align)` sur les fonctions. Ceci était toujours ignoré, mais à présent cela génère une erreur du compilateur.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Pour résoudre ce problème, supprimez `__declspec(align)` de la déclaration de fonction. Comme cela n'avait aucun effet, la suppression ne change rien.  
  
-   **Gestion des exceptions**  
  
     Quelques modifications ont été apportées à la gestion des exceptions. Tout d'abord, les objets d'exception doivent pouvoir être copiés ou déplacés. Le code suivant pouvait être compilé dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], mais ne le peut pas dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] :  
  
    ```  
    struct S {  
    public:  
        S();  
    private:  
        S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     Le problème est que le constructeur de copie est privé, si bien que l'objet ne peut pas être copié comme dans le cours normal de la gestion d'une exception. La même règle s'applique quand le constructeur de copie est déclaré `explicit`.  
  
    ```  
    struct S {  
        S();  
        explicit S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     Pour mettre à jour votre code, assurez-vous que le constructeur de copie de votre objet d'exception est public et qu'il n'est pas marqué `explicit`.  
  
     L'interception d'une exception par sa valeur exige que l'objet d'exception puisse être copié. Le code suivant pouvait être compilé dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], mais ne le peut pas dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] :  
  
    ```  
    struct B {  
    public:  
        B();  
    private:  
        B(const B &);  
    };  
  
    struct D : public B {  
    };  
  
    int main()  
    {  
        try  
        {  
        }  
        catch (D d) // error  
        {  
        }  
    }  
  
    ```  
  
     Vous pouvez résoudre ce problème en remplaçant le type de paramètre pour `catch` par une référence.  
  
    ```  
    catch(D& d)  
    {  
    }  
    ```  
  
-   **Littéraux de chaîne suivis par des macros**  
  
     Le compilateur prend désormais en charge les littéraux définis par l'utilisateur. Par conséquent, les littéraux de chaîne suivis par des macros sans espace blanc intermédiaire sont interprétés comme des littéraux définis par l'utilisateur, qui peuvent entraîner des erreurs ou des résultats inattendus. Par exemple, dans les compilateurs précédents, le code suivant pouvait être compilé avec succès :  
  
    ```  
    #define _x "there"  
    char* func() {  
        return "hello"_x;  
    }  
    int main()  
    {  
        char * p = func();  
        return 0;  
    }  
    ```  
  
     Le compilateur interprétait cela comme un littéral de chaîne « hello » suivi par une macro, correspondant à « there » étendu, puis les deux littéraux de chaîne étaient concaténés en un seul. Dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], le compilateur interprète cela comme un littéral défini par l'utilisateur, mais comme il n'existe aucun littéral défini par l'utilisateur correspondant _x défini, il génère une erreur.  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     Pour résoudre ce problème, ajoutez un espace entre le littéral de chaîne et la macro.  
  
-   **Littéraux de chaîne adjacents**  
  
     Comme précédemment, en raison des modifications associées dans l'analyse des chaînes, les littéraux de chaîne adjacents (littéraux de chaîne aux caractères larges ou étroits) sans espace blanc étaient interprétés comme une chaîne concaténée unique dans les versions antérieures de Visual C++. Dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], vous devez à présent ajouter un espace blanc entre les deux chaînes. Par exemple, le code suivant doit être modifié :  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     Ajoutez simplement un espace entre les deux chaînes.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Placement new et delete**  
  
     Une modification a été apportée à l'opérateur delete afin de le mettre en conformité avec la norme C++14. Vous trouverez les détails relatifs au changement de normes sur la page décrivant la [libération dimensionnée C++](http://isocpp.org/files/papers/n3778.html). Les modifications ajoutent une forme de l'opérateur delete global qui accepte un paramètre de taille. La modification avec rupture tient au fait que si vous utilisiez précédemment un opérateur delete avec la même signature (pour correspondre à un opérateur placement new), vous recevrez une erreur de compilation (C2956, qui se produit au point où l'opérateur placement new est utilisé, étant donné qu'il s'agit de la position dans le code où le compilateur tente d'identifier un opérateur delete correspondant approprié).  
  
     La fonction `void operator delete(void *, size_t)` était un opérateur placement delete correspondant à la fonction placement new « void \* operator new(size_t, size_t) » dans C++11. Avec la désallocation dimensionnée C++14, cette fonction delete est à présent une *fonction de désallocation habituelle* (opérateur delete global). La norme impose que si l'utilisation d'un opérateur placement new recherche une fonction delete correspondante et trouve une fonction de désallocation habituelle, le programme est incorrect.  
  
     Par exemple, supposons que votre code définit à la fois un opérateur placement new et un opérateur placement delete :  
  
    ```  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     Le problème se produit en raison de la correspondance dans les signatures de fonction entre un opérateur placement delete que vous avez défini et le nouvel opérateur delete dimensionné global. Envisagez d'utiliser un autre type que size_t pour n'importe quel opérateur placement new ou delete.  Notez que le type du typedef size_t dépend du compilateur. Il s'agit d'un typedef pour unsigned int dans Visual C++. Il est recommandé d'utiliser un type énuméré tel que :  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     Ensuite, modifiez votre définition de placement new et delete pour utiliser ce type comme second argument à la place de size_t. Vous devez également mettre à jour les appels à placement new pour transmettre le nouveau type (par exemple, en utilisant `static_cast<my_type>` pour effectuer une conversion à partir de la valeur entière) et mettre à jour la définition de new et delete pour effectuer un cast en retour vers le type entier. Vous n'avez pas besoin d'utiliser un enum pour cela. Un type de classe avec un membre size_t fonctionne également.  
  
     Une autre solution consiste à éliminer l'opération placement new complète. Si votre code utilise placement new pour implémenter un pool de mémoires où l'argument de positionnement est la taille de l'objet qui est alloué ou supprimé, la fonction de désallocation dimensionnée peut être appropriée pour remplacer votre propre code de pool de mémoires personnalisé, et vous pouvez vous débarrasser des fonctions de positionnement et utiliser simplement votre propre opérateur delete à deux arguments à la place des fonctions de positionnement.  
  
     Si vous ne voulez pas mettre à jour votre code immédiatement, vous pouvez revenir à l'ancien comportement en utilisant l'option de compilateur /Zc:sizedDealloc-. Si vous utilisez cette option, les fonctions delete à deux arguments n'existent pas et ne causeront pas de conflit avec votre opérateur placement delete.  
  
-   **Membres de données d’union**  
  
     Les membres de données d'unions ne peuvent plus posséder de types de référence. Il était possible de compiler le code suivant dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], mais il génèrait une erreur dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
    ```  
    union U1 {  
        const int i;  
    };  
    union U2 {  
       int &i;  
    };  
    union U3 {  
        struct {int &i;};  
    };  
    ```  
  
     Le code précédent génère les erreurs suivantes :  
  
    ```Output  
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type  
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type  
    ```  
  
     Pour résoudre ce problème, modifiez les types de référence en spécifiant un pointeur ou une valeur. La modification du type en pointeur nécessite des modifications dans le code qui utilise le champ union. La modification du code en valeur modifierait les données stockées dans l'union, ce qui affecte les autres champs dans la mesure où les champs dans les types d'union partagent la même mémoire. Selon la taille de la valeur, cela peut également modifier la taille de l'union.  
  
-   Les unions anonymes sont à présent plus conformes à la norme. Les versions précédentes du compilateur généraient un constructeur explicite et un destructeur pour les unions anonymes. Ceux-ci sont supprimés dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
    ```  
    struct S {  
      S();  
     };  
  
     union {  
      struct {  
       S s;  
      };  
     } u; // C2280  
    ```  
  
     Le code précédent génère l'erreur suivante dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] :  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     Pour résoudre ce problème, fournissez vos propres définitions du constructeur et/ou du destructeur.  
  
    ```  
    struct S {  
    // Provide a default constructor by adding an empty function body.  
    S() {}   
    };  
  
    union {  
    struct {  
    S s;  
    };  
    } u;  
    ```  
  
-   **Unions avec structs anonymes**  
  
     Pour se conformer à la norme, le comportement d'exécution a changé pour les membres de structures anonymes dans les unions. Le constructeur pour les membres de structure anonymes dans une union n'est plus implicitement appelé lors de la création d'une telle union. De plus, le destructeur pour les membres de structure anonymes dans une union n'est plus implicitement appelé quand l'union passe hors de portée. Considérons le code suivant, dans lequel une union U contient une structure anonyme contenant un membre qui est une structure nommée S possèdant un destructeur.  
  
    ```  
    #include <stdio.h>  
    struct S {  
        S() { printf("Creating S\n"); }  
        ~S(){ printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
        S s;  
    };  
        U() {}  
        ~U(){}  
    };  
  
    void f()  
    {  
        U u;  
        // Destructor implicitly called here.  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     Dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], le constructeur de S est appelé quand l'union est créée, et le destructeur de S est appelé quand la pile pour la fonction f est nettoyée. Mais, dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], le constructeur et le destructeur ne sont pas appelés. Le compilateur émet un avertissement à propos de ce changement de comportement.  
  
    ```Output  
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called  
    ```  
  
     Pour restaurer le comportement d'origine, nommez la structure anonyme. Le comportement d'exécution des structures non anonymes est le même, quelle que soit la version du compilateur.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        S() { printf("Creating S.\n"); }  
        ~S() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        } namedStruct;  
        U() {}  
        ~U() {}  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     Sinon, essayez de déplacer le code du constructeur et du destructeur dans de nouvelles fonctions et ajoutez des appels à ces fonctions à partir du constructeur et du destructeur pour l'union.  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        void Create() { printf("Creating S.\n"); }  
        void Destroy() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        };  
        U() { s.Create();  }  
        ~U() { s.Destroy(); }  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
    char s[1024];  
    printf("Press any key.\n");  
    gets_s(s);  
    return 0;  
    }  
    ```  
  
-   **Résolution de modèle**  
  
     Des modifications ont été apportées à la résolution de noms pour les modèles. En C++, quand vous envisagez des candidats pour la résolution d'un nom, il peut arriver qu'un ou plusieurs noms considérés comme des correspondances potentielles produisent une instanciation de modèle non valide. Ces instanciations non valides ne provoquent normalement pas d'erreurs du compilateur, un principe appelé SFINAE (Substitution Failure Is Not An Error).  
  
     À présent, si le principe SFINAE exige que le compilateur instancie la spécialisation d'un modèle de classe, toutes les erreurs qui surviennent au cours de ce processus sont des erreurs du compilateur. Dans les versions précédentes, le compilateur ignore de telles erreurs. Considérons par exemple le code suivant :  
  
    ```  
    #include <type_traits>  
  
    template<typename T>  
    struct S  
    {  
    S() = default;  
    S(const S&);  
    S(S&&);  
  
    template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type>  
    S(S<U>&&);  
    };  
  
    struct D;  
  
    void f1()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    struct B  
    {  
    };  
  
    struct D : public B  
    {  
    };  
  
    void f2()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    ```  
  
     Si vous effectuez une compilation avec le compilateur actuel, vous obtenez l'erreur suivante :  
  
    ```Output  
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'  
    ..\t331.cpp(14): note: see declaration of 'D'  
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled  
            with  
            [  
                T=D,  
                U=D  
            ]  
    ```  
  
     La raison en est qu'au point de la première invocation de is_base_of, la classe 'D' n'a pas encore été définie.  
  
     Dans ce cas, la correction proposée consiste à ne pas utiliser type traits tant que la classe n’a pas été définie. Si vous placez les définitions de B et D au début du fichier de code, l’erreur est résolue. Si les définitions sont dans des fichiers d'en-tête, vérifiez l'ordre des instructions include pour les fichiers d'en-tête afin de vous assurer que toutes les définitions de classe sont compilées avant l'utilisation des modèles problématiques.  
  
-   **Constructeurs de copie**  
  
     Dans [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] et Visual Studio 2015, le compilateur génère un constructeur de copie pour une classe si celle-ci a un constructeur de déplacement défini par l’utilisateur, mais aucun constructeur de copie personnalisé. Dans Dev14, ce constructeur de copie généré implicitement est également marqué « = delete ».  
  
##  <a name="VS_Update1"></a> Améliorations de la conformité dans Update 1  
  
-   **Classes de base virtuelles privées et héritage indirect**  
  
     Les versions précédentes du compilateur autorisaient une classe dérivée à appeler des fonctions membres de ses classes de base *dérivées indirectement*`private virtual` . Cet ancien comportement était incorrect et non conforme à la norme C++. Le compilateur n’accepte plus de code écrit de cette façon. Il émet dans ce cas l’erreur du compilateur C2280.  
  
    ```Output  
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    class base  
    {  
    protected:  
        base();  
        ~base();  
    };  
  
    class middle: private virtual base {};class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  //   
    }  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    class base;  // as above  
  
    class middle: protected virtual base {};  
    class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
     - ou -  
  
    ```  
    class base;  // as above  
  
    class middle: private virtual base {};  
    class top: public virtual middle, private virtual bottom {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
-   **Opérateurs new et delete surchargés**  
  
     Avec les versions précédentes du compilateur, vous pouviez déclarer un `operator new` non membre et un `operator delete` non membre comme static, et vous pouviez les déclarer dans des espaces de noms autres que l’espace de noms global.  Cet ancien comportement créé un risque que le programme n’appelle pas l’implémentation de l’opérateur `new` ou `delete` prévue par le programmeur, entraînant ainsi un comportement incorrect en mode silencieux. Le compilateur n’accepte plus de code écrit de cette façon. Au lieu de cela, il émet l’erreur du compilateur C2323.  
  
    ```Output  
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'  
    ```  
  
     De plus, bien que le compilateur ne donne pas de diagnostic spécifique, l’opérateur new inline est considéré comme incorrect.  
  
-   **Appel de 'operator *type*()' (conversion définie par l’utilisateur) sur des types autres que des types classe**  
  
     Les versions précédentes du compilateur autorisaient l’appel de ’operator *type*()’ sur des types autres que des types classe et ignoraient cet appel en silence. Cet ancien comportement créait un risque de génération de code incorrect en mode silencieux qui provoquait un comportement imprévisible au moment de l’exécution. Le compilateur n’accepte plus de code écrit de cette façon. Au lieu de cela, il émet l’erreur du compilateur C2228.  
  
    ```Output  
    error C2228: left of '.operator type' must have class/struct/union  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column.operator index_t());  // error C2228  
    }  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'  
    }  
    ```  
  
-   **Typename redondant dans les spécificateurs de type élaborés**  
  
     Les versions précédentes du compilateur autorisaient `typename` dans les spécificateurs de type élaborés. Le code écrit de cette manière est sémantiquement incorrect. Le compilateur n’accepte plus de code écrit de cette façon. Au lieu de cela, il émet l’erreur du compilateur C3406.  
  
    ```Output  
    error C3406: 'typename' cannot be used in an elaborated type specifier  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    template <typename class T>  
    class container;  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case  
    class container;  
    ```  
  
-   **Déduction de type des tableaux à partir d’une liste d’initialiseurs**  
  
     Les versions précédentes du compilateur ne prenaient pas en charge la déduction de type des tableaux à partir d’une liste d’initialiseurs. Le compilateur prend désormais en charge cette forme de déduction de type. Ainsi, les appels à des modèles de fonctions à l’aide de listes d’initialiseurs peuvent maintenant être ambigus ou une surcharge autre que dans les versions précédentes du compilateur peut être choisie. Pour résoudre ces problèmes, le programme doit maintenant spécifier explicitement la surcharge prévue par le programmeur.  
  
     Lorsque, à cause de ce nouveau comportement, la résolution de surcharge prend en compte un candidat supplémentaire qui est tout aussi efficace que le candidat historique, l’appel devient ambigu et le compilateur émet l’erreur C2668.  
  
    ```Output  
    error C2668: 'function' : ambiguous call to overloaded function.  
    ```  
  
     Exemple 1 : appel ambigu à une fonction surchargée (avant)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now considers this call ambiguous, and issues a compiler error  
        f({3});  error C2668: 'f' ambiguous call to overloaded function  
    }  
    ```  
  
     Exemple 1 : appel ambigu à une fonction surchargée (après)  
  
    ```cpp  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.  
        f(3);  
    }  
    ```  
  
     Lorsque, à cause de ce nouveau comportement, la résolution de surcharge prend en compte un candidat supplémentaire qui est une meilleure correspondance que le candidat historique, l’appel résout sans ambiguïté le nouveau candidat, ce qui provoque une modification du comportement du programme probablement différente de ce que le programmeur a prévu.  
  
     Exemple 2 : modification de la résolution de surcharge (avant)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)  
    struct S  
    {  
        int i;  
        int j;  
    };  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead  
        f({1, 2});  
    }  
    ```  
  
     Exemple 2 : modification de la résolution de surcharge (après)  
  
    ```cpp  
    struct S;  // as before  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.  
        f(S{1, 2});  
    }  
    ```  
  
-   **Restauration des avertissements d’instruction switch**  
  
     Une version précédente du compilateur supprimait les avertissements préexistants liés aux instructions `switch` . Ces avertissements ont été restaurés. Le compilateur émet désormais les avertissements restaurés, et les avertissements liés à des cas spécifiques (notamment le cas par défaut) sont désormais émis sur la ligne contenant le cas qui pose problème, plutôt que sur la dernière ligne de l’instruction switch. Comme ces avertissements ne sont plus émis sur les mêmes lignes qu’auparavant, les avertissements précédemment supprimés à l’aide de `#pragma warning(disable:####)` peuvent ne plus être supprimés comme prévu. Pour supprimer ces avertissements comme prévu, vous devrez peut-être déplacer la directive `#pragma warning(disable:####)` vers une ligne au-dessus du premier cas potentiellement incriminé. Voici les avertissements restaurés.  
  
    ```Output  
    warning C4060: switch statement contains no 'case' or 'default' labels  
    ```  
  
    ```Output  
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label  
    ```  
  
    ```Output  
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled  
    ```  
  
    ```Output  
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'  
    ```  
  
    ```Output  
    warning C4064: switch of incomplete enum 'flags'  
    ```  
  
    ```Output  
    warning C4065: switch statement contains 'default' but no 'case' labels  
    ```  
  
    ```Output  
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'  
    ```  
  
    ```Output  
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given  
    ```  
  
     Exemple d’avertissement C4063 (avant)  
  
    ```cpp  
    class settings  
    {  
    public:  
        enum flags  
        {  
            bit0 = 0x1,  
            bit1 = 0x2,  
            ...  
        };  
        ...  
    };  
  
    int main()  
    {  
        auto val = settings::bit1;  
  
        switch (val)  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // warning C4063  
            break;  
        }  
    };  
    ```  
  
     Exemple d’avertissement C4063 (après)  
  
    ```cpp  
    class settings {...};  // as above  
  
    int main()  
    {  
        // since C++11, use std::underlying_type to determine the underlying type of an enum  
        typedef std::underlying_type<settings::flags>::type flags_t;  
  
        auto val = settings::bit1;  
  
        switch (static_cast<flags_t>(val))  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // ok  
            break;  
        }  
    };  
    ```  
  
     Des exemples des autres avertissements restaurés sont fournis dans leur documentation.  
  
-   **#include : utilisation du spécificateur de répertoire parent ’..’ dans le chemin d’accès** (affecte uniquement /Wall /WX)  
  
     Les versions précédentes du compilateur ne détectaient pas l’utilisation du spécificateur de répertoire parent ’..’ dans le chemin d’accès des directives  `#include` . Le code écrit de cette manière est généralement conçu pour inclure des en-têtes qui existent en dehors du projet en utilisant de manière incorrecte des chemins d’accès relatifs au projet. Cet ancien comportement créait un risque que le programme puisse être compilé en incluant un fichier source différent de celui prévu par le programmeur, ou que ces chemins d’accès relatifs ne soient pas portables vers d’autres environnements de génération. Désormais, le compilateur détecte et informe le programmeur du code écrit de cette façon, et il émet un avertissement C4464 facultatif si cette fonctionnalité est activée.  
  
    ```Output  
    warning C4464: relative include path contains '..'  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    #include "..\headers\C4426.h"  // emits warning C4464  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories  
    ```  
  
     De plus, bien que le compilateur ne donne pas de diagnostic spécifique, nous vous recommandons également de ne pas utiliser le spécificateur de répertoire parent ".." pour spécifier les répertoires Include de votre projet.  
  
-   **#pragma optimize() s’étend au-delà de la fin du fichier d’en-tête** (affecte uniquement /Wall /WX)  
  
     Les versions précédentes du compilateur ne détectaient pas les modifications apportées aux paramètres de l’indicateur d’optimisation qui échappent un fichier d’en-tête inclus dans une unité de traduction. Désormais, le compilateur détecte et informe le programmeur du code écrit de cette façon, et il émet un avertissement C4426 facultatif à l’emplacement du `#include`incriminé, si cette fonctionnalité est activée. Cet avertissement est émis uniquement si le modifications entrent en conflit avec les indicateurs d’optimisation définis par des arguments de ligne de commande au compilateur.  
  
    ```Output  
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  // warning C4426  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  
    ```  
  
-   **Incompatibilité de #pragma warning(push)** et **#pragma warning(pop)** (affecte uniquement /Wall /WX)  
  
     Les versions précédentes du compilateur ne détectaient pas les associations des modifications d’état `#pragma warning(push)` aux modifications d’état `#pragma warning(pop)` dans un autre fichier source, qui sont rarement souhaitées. Cet ancien comportement créait un risque que le programme soit compilé avec un autre ensemble d’avertissements activé que celui prévu par le programmeur, ce qui pouvait provoquer un comportement incorrect en mode silencieux. Désormais, le compilateur détecte et informe le programmeur du code écrit de cette façon, et il émet un avertissement C5031 facultatif à l’emplacement du `#pragma warning(pop)` correspondant, si cette fonctionnalité est activée. Cet avertissement inclut une note faisant référence à l’emplacement du #pragma warning(push) correspondant.  
  
    ```Output  
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    ...  
    #pragma warning(pop)  // pops a warning state not pushed in this source file   
    ...  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'  
    ...  
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031  
    ...  
  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  // pops the warning state pushed in this source file  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    #pragma warning(push)  // pushes the warning state pushed in this source file  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.  
    ...  
    #include "C5031_part2.h"  
    ...  
  
    ```  
  
     Bien que rare, le code écrit de cette manière est parfois intentionnel. Le code écrit de cette manière est sensible aux modifications de l’ordre de `#include`. Dans la mesure du possible, nous conseillons que les fichiers de code source gèrent l’état d’avertissement de façon autonome.  
  
-   **#pragma warning(push) sans correspondance** (affecte uniquement /Wall /WX)  
  
     Les versions précédentes du compilateur ne détectaient pas les modifications d’état `#pragma warning(push)` sans correspondance à la fin d’une unité de traduction. Désormais, le compilateur détecte et informe le programmeur du code écrit de cette façon, et il émet un avertissement C5032 facultatif à l’emplacement du #pragma warning(push) sans correspondance, si cette fonctionnalité est activée. Cet avertissement est émis uniquement s’il n’y a aucune erreur de compilation dans l’unité de traduction.  
  
    ```Output  
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5032.h ends without #pragma warning(pop)  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop) // matches #pragma warning (push) on line 1  
    // C5032.h ends  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)  
    ```  
  
-   **Des avertissements supplémentaires peuvent être émis à la suite du suivi d’état du #pragma warning amélioré**  
  
     Les versions précédentes du compilateur ne suivaient pas les modifications de l’état d’avertissement #pragma assez bien pour émettre tous les avertissements prévus. Ce comportement créait un risque que certains avertissements soient supprimés dans des circonstances autres que celles prévues par le programmeur. Le compilateur effectue maintenant le suivi de l’état d’avertissement #pragma de manière plus robuste, tout particulièrement en ce qui concerne les modifications de l’état d’avertissement #pragma dans les modèles, et il émet éventuellement de nouveaux avertissements C5031 et C5032 destinés à aider le programmeur à identifier les utilisations involontaires de `#pragma warning(push)` et `#pragma warning(pop)`.  
  
     Grâce à l’amélioration du suivi des modifications de l’état d’avertissement #pragma, les avertissements qui étaient auparavant supprimés de manière incorrecte ou ceux liés à des problèmes anciennement mal diagnostiqués peuvent maintenant être émis.  
  
-   **Amélioration de l’identification du code inaccessible**  
  
     Les modifications apportées à la bibliothèque standard C++ et la capacité améliorée à intégrer des appels de fonction par rapport aux versions précédentes du compilateur peuvent permettre au compilateur de prouver que du code est désormais inaccessible. Ce nouveau comportement peut provoquer des instances nouvelles et plus fréquentes de l’avertissement C4720.  
  
    ```Output  
    warning C4720: unreachable code  
    ```  
  
     Dans de nombreux cas, cet avertissement peut être émis uniquement lors de la compilation avec les optimisations activées, car les optimisations peuvent intégrer plus d’appels de fonction, supprimer le code redondant ou permettre de déterminer que du code est inaccessible. Nous avons constaté que de nouvelles instances de l’avertissement C4720 étaient fréquentes dans des blocs try/catch, en particulier en cas d’utilisation de [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True).  
  
     Exemple (avant)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // ok   
    }  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // warning C4702: unreachable code  
    }  
    ```  
  
##  <a name="VS_Update2"></a> Améliorations de la conformité dans Update 2  
  
-   **Des erreurs et avertissements supplémentaires peuvent être générés en raison de la prise en charge partielle de l’expression SFINAE.**  
  
     Dans les versions précédentes du compilateur, certains types d’expressions au sein des spécificateurs `decltype` n’étaient pas analysés en raison de l’absence de prise en charge de l’expression SFINAE. Cet ancien comportement était incorrect et non conforme à la norme C++. À présent, le compilateur analyse ces expressions et offre une prise en charge partielle de l’expression SFINAE grâce à certaines améliorations récentes de la conformité. Par conséquent, le compilateur génère maintenant des avertissements et des erreurs détectés dans des expressions qui n’étaient pas analysées dans les versions précédentes du compilateur.  
  
     Quand ce nouveau comportement analyse une expression `decltype` comportant un type qui n’a pas encore été déclaré, le compilateur génère l’erreur de compilateur C2039.  
  
    ```Output  
    error C2039: 'type': is not a member of '`global namespace''  
    ```  
  
     Exemple 1 : utilisation d’un type non déclaré (avant)  
  
    ```cpp  
    struct s1  
    {  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  // error C2039  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     Exemple 1 (après)  
  
    ```cpp  
    struct s1  
    {  
      template <typename>  // forward declare s2struct s2;  
  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     Quand ce nouveau comportement analyse une expression `decltype` dans laquelle il manque le mot clé `typename` obligatoire pour spécifier qu’un nom dépendant est un type, le compilateur génère l’avertissement de compilateur C4346 en même temps que l’erreur de compilateur C2923.  
  
    ```Output  
    warning C4346: 'S2<T>::Type': dependent name is not a type  
    ```  
  
    ```Output  
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'  
    ```  
  
     Exemple 2 : le nom dépendant n’est pas un type (avant)  
  
    ```cpp  
    template <typename T>  
    struct s1  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    struct s2  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<S2<T>::type>::type>()));  // warning C4346, error C2923  
    };  
    ```  
  
     Exemple 2 (après)  
  
    ```cpp  
    template <typename T> struct s1 {...};  // as above  
    template <typename T> struct s2 {...};  // as above  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<typename S2<T>::type>::type>()));  
    };  
    ```  
  
-   Les variables membres `volatile`  **n’autorisent pas les constructeurs et les opérateurs d’assignation définis implicitement**  
  
     Dans les versions précédentes du compilateur, il était possible de générer automatiquement les constructeurs de copie/déplacement par défaut et les opérateurs d’assignation de copie/déplacement par défaut pour une classe contenant des variables membres `volatile`. Cet ancien comportement était incorrect et non conforme à la norme C++. À présent, le compilateur considère qu’une classe avec des variables de membre volatiles a des opérateurs de construction et d’assignation non triviaux, ce qui empêche la génération automatique des implémentations par défaut de ces opérateurs.  Quand une telle classe est membre d’une union (ou d’une union anonyme au sein d’une classe), les constructeurs de copie/déplacement et les opérateurs d’assignation de copie/déplacement de l’union (ou de la classe contenant l’union anonyme) sont implicitement définis comme étant supprimés. Toute tentative de construction ou de copie de l’union (ou de la classe contenant l’union anonyme) sans avoir défini explicitement les constructeurs ou opérateurs est considérée comme une erreur. Le compilateur génère alors l’erreur de compilateur C2280.  
  
    ```Output  
    error C2280: 'B::B(const B &)': attempting to reference a deleted function  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    struct A  
    {  
      volatile int i;  
      volatile int j;  
    };  
  
    extern A* pa;  
  
    struct B  
    {  
      union  
      {  
        A a;  
        int i;  
      };  
    };  
  
    B b1 {*pa};  
    B b2 (b1);  // error C2280  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    struct A  
    {  
      int i;int j;  
    };  
  
    extern volatile A* pa;  
  
    A getA()  // returns an A instance copied from contents of pa  
    {  
      A a;  
      a.i = pa->i;  
      a.j = pa->j;  
      return a;  
    }  
  
    struct B;  // as above  
  
    B b1 {GetA()};  
    B b2 (b1);  // error C2280  
    ```  
  
-   **Les fonctions membres statiques ne prennent pas en charge les qualificateurs cv.**  
  
     Dans les versions précédentes de Visual C++ 2015, les fonctions membres statiques pouvaient contenir des qualificateurs cv. Ce comportement est dû à une régression effectuée dans Visual C++ 2015 et dans Visual C++ 2015 Update 1. Le code écrit de cette manière est refusé dans Visual C++ 2013 et les versions antérieures de Visual C++. Le comportement de Visual C++ 2015 et de Visual C++ 2015 Update 1 est incorrect, et n’est pas conforme à la norme C++.  Visual Studio 2015 Update 2 refuse le code écrit de cette façon et génère l’erreur de compilateur C2511.  
  
    ```Output  
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'  
    ```  
  
     Exemple (avant)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() const {}  // C2511  
  
    ```  
  
     Exemple (après)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() {}  // removed const  
  
    ```  
  
-   **La déclaration anticipée d’enum n’est pas autorisée dans le code de WinRT** (concerne /ZW uniquement)  
  
     Le code compilé pour le Windows Runtime (WinRT) n’autorise pas la déclaration anticipée des types `enum`, comme lors de la compilation de code C++ managé pour le .Net Framework à l’aide du commutateur du compilateur /clr. Ce comportement garantit que la taille d’une énumération est toujours connue et qu’elle peut être projetée correctement vers le système de type WinRT. Le compilateur refuse le code écrit de cette façon et génère l’erreur de compilateur C2599 ainsi que l’erreur de compilateur C3197.  
  
    ```Output  
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed  
    ```  
  
    ```Output  
    error C3197: 'public': can only be used in definitions  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    namespace A {  
      public enum class CustomEnum: int32;  // forward declaration; error C2599, error C3197  
    }  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
     Exemple (après)  
  
    ```cpp  
              // forward declaration of CustomEnum removed  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
-   **L’opérateur non membre surchargé new et l’opérateur delete ne peuvent pas être déclarés inline**. Niveau 1 (/W1) activé par défaut.  
  
     Les versions précédentes du compilateur ne génèrent pas d’avertissement quand les fonctions d’opérateur non membre new et d’opérateur delete sont déclarées inline. Le code écrit de cette manière est incorrect (aucun diagnostic requis) et peut provoquer des problèmes de mémoire en raison de l’incompatibilité entre les opérateurs new et delete (en particulier, s’ils sont associés à la désallocation dimensionnée), qui peut être difficile à diagnostiquer.   À présent, le compilateur génère l’avertissement C4595 pour faciliter l’identification du code écrit de cette manière.  
  
    ```Output  
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
              inline void* operator new(size_t sz)  // warning C4595  
    {  
      ...  
    }  
    ```  
  
     Exemple (après)  
  
    ```cpp  
              void* operator new(size_t sz)  // removed inline  
    {  
      ...  
    }  
    ```  
  
     Pour corriger le code écrit de cette manière, vous devrez peut-être déplacer les définitions d’opérateur du fichier d’en-tête vers le fichier source correspondant.  
  
##  <a name="VS_Update3"></a> Améliorations de la conformité dans Update 3  
  
-   **std::is_convertable détecte désormais l’auto-affectation** (bibliothèque standard)  
  
     Les versions précédentes du trait de type `std::is_convertable` ne détectent pas correctement l’auto-affectation d’un type de classe quand son constructeur de copie est supprimé ou privé. Maintenant, `std::is_convertable<>::value` est correctement défini sur `false` quand il est appliqué à un type de classe avec un constructeur de copie supprimé ou privé.  
  
     Aucun diagnostic du compilateur n’est associé à cette modification.  
  
     Exemple  
  
    ```cpp  
    #include <type_traits>  
  
    class X1  
    {  
    public:  
        X1(const X1&) = delete;  
    };  
  
    class X2  
    {  
    private:  
        X2(const X2&);  
    };  
  
    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");  
    ```  
  
     Dans les versions précédentes de Visual C++, les assertions statiques en bas de cet exemple réussissent, car `std::is_convertable<>::value` a été incorrectement défini sur `true`. Maintenant, `std::is_convertable<>::value` est correctement défini sur `false`, ce qui entraîne l’échec des assertions statiques.  
  
-   **Les constructeurs de copie et de déplacement ordinaires supprimés ou par défaut respectent les spécificateurs d’accès**  
  
     Les versions précédentes du compilateur ne contrôlaient pas le spécificateur d’accès des constructeurs de copie et de déplacement ordinaires supprimés ou par défaut avant de les autoriser à être appelés. Cet ancien comportement était incorrect et non conforme à la norme C++. Dans certains cas, cet ancien comportement créait un risque de génération de code incorrect en mode silencieux qui provoquait un comportement imprévisible au moment de l’exécution. Le compilateur vérifie désormais le spécificateur d’accès des constructeurs de copie et de déplacement ordinaires supprimés ou par défaut pour déterminer s’ils peuvent être appelés et, dans le cas contraire, émet l’avertissement de compilateur C2248 en conséquence.  
  
    ```Output  
    error C2248: 'S::S' cannot access private member declared in class 'S'  
    ```  
  
     Exemple (avant)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(S);  // pass S by value  
  
    int main()  
    {  
        S s;  
        f(s);  // error C2248, can't invoke private copy constructor  
    }  
    ```  
  
     Exemple (après)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(const S&);  // pass S by reference  
  
    int main()  
    {  
        S s;  
        f(s);  
    }  
    ```  
  
-   **Dépréciation de la prise en charge du code ATL avec attributs**. Niveau 1 (/W1) activé par défaut.  
  
     Les versions précédentes du compilateur prenaient en charge le code ATL avec attributs. Comme phase suivante de la suppression de la prise en charge du code ATL avec attributs qui [est apparue dans Visual C++ 2008](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx), le code ATL avec attributs a été déprécié. Le compilateur émet désormais l’avertissement C4467 pour faciliter l’identification de ce type de code déprécié.  
  
    ```Output  
    warning C4467: Usage of ATL attributes is deprecated  
    ```  
  
     Si vous souhaitez continuer à utiliser le code ATL avec attributs jusqu’à ce que la prise en charge soit supprimée du compilateur, vous pouvez désactiver cet avertissement en transmettant les arguments de ligne de commande `/Wv:18` ou `/wd4467` au compilateur, ou en ajoutant `#pragma warning(disable:4467)` à votre code source.  
  
     Exemple 1 (avant)  
  
    ```cpp  
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]  
    class A {};  
    ```  
  
     Exemple 1 (après)  
  
    ```cpp  
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};  
  
    ```  
  
     Vous devez ou voulez parfois créer un fichier IDL pour éviter d’utiliser les attributs ATL dépréciés, comme dans l’exemple de code ci-dessous  
  
     Exemple 2 (avant)  
  
    ```cpp  
    [emitidl];  
    [module(name="Foo")];  
  
    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
    __interface ICustom {  
        HRESULT Custom([in] long l, [out, retval] long *pLong);  
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);  
    };  
  
    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
    class CFoo : public ICustom  
    {  
        // ...  
    };  
    ```  
  
     Tout d’abord, créez le fichier *.idl ; le fichier vc140.idl généré peut être utilisé pour obtenir un fichier \*.idl contenant les interfaces et les annotations.  
  
     Ajoutez ensuite une étape MIDL à votre génération pour vérifier que les définitions d’interface C++ sont générées.  
  
     Exemple 2, IDL (après)  
  
    ```cpp  
    import "docobj.idl";  
  
    [  
        object,local,uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)  
    ]  
  
    interface ICustom : IUnknown {  
        HRESULT  Custom([in] long l, [out,retval] long *pLong);  
        [local] HRESULT  CustomLocal([in] long l, [out,retval] long *pLong);  
    };  
  
    [ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]  
    library Foo  
    {  
        importlib("stdole2.tlb");  
        importlib("olepro32.dll");  
            [  
                version(1.0),  
                appobject,uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)  
            ]  
  
        coclass CFoo {  
            interface ICustom;  
        };  
    }  
    ```  
  
     Utilisez ensuite ATL directement dans le fichier d’implémentation, comme dans l’exemple de code ci-dessous.  
  
     Exemple 2, implémentation (après)  
  
    ```cpp  
    #include <idl.header.h>  
    #include <atlbase.h>  
  
    class ATL_NO_VTABLE CFooImpl :  
        public ICustom,  
        public ATL::CComObjectRootEx<CComMultiThreadModel>  
    {  
    public:  
        BEGIN_COM_MAP(CFooImpl)  
        COM_INTERFACE_ENTRY(ICustom)  
        END_COM_MAP()  
    };  
    ```  
  
-   **Fichiers d’en-tête précompilés (PCH) et directives #include incompatibles** (affecte uniquement /Wall /WX)  
  
     Les versions précédentes du compilateur acceptaient les directives `#include` incompatibles dans les fichiers sources entre les compilations `-Yc` et `-Yu` lors de l’utilisation de fichiers d’en-tête précompilés (PCH). Le code écrit de cette façon n’est plus accepté par le compilateur.   Le compilateur émet désormais l’avertissement CC4598 pour faciliter l’identification des directives `#include` incompatibles lors de l’utilisation de fichiers PCH.  
  
    ```Output  
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position  
    ```  
  
     Exemple (avant) :  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"  
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "b.h"  
    #include "a.h"  // mismatched order relative to X.cpp  
    #include "c.h"  
    ```  
  
     Exemple (après)  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"   
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h" // matched order relative to X.cpp  
    #include "c.h"  
    ```  
  
-   **Fichiers d’en-tête précompilés (PCH) et répertoires Include incompatibles** (affecte uniquement /Wall /WX)  
  
     Les versions précédentes du compilateur acceptaient les arguments de ligne de commande des répertoires Include `-I` incompatibles passés au compilateur entre les compilations `-Yc` et `-Yu` lors de l’utilisation de fichiers d’en-tête précompilés (PCH). Le code écrit de cette façon n’est plus accepté par le compilateur.   Le compilateur émet désormais l’avertissement CC4599 pour faciliter l’identification des arguments de ligne de commande des répertoires Include (`-I`) incompatibles lors de l’utilisation de fichiers PCH.  
  
    ```Output  
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position  
    ```  
  
     Exemple (avant)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h Z.cpp  
    ```  
  
     Exemple (après)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h -I.. Z.cpp  
    ```