---
title: "Modifications avec rupture dans Visual&#160;C++&#160;2015 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "modifications avec rupture (C++)"
ms.assetid: b38385a9-a483-4de9-99a6-797488bc5110
caps.latest.revision: 124
caps.handback.revision: 117
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifications avec rupture dans Visual&#160;C++&#160;2015
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous effectuez une mise à niveau vers une nouvelle version du compilateur Visual C\+\+, vous pouvez rencontrer des erreurs de compilation et\/ou d'exécution dans du code qui pouvait auparavant être compilé et exécuté correctement. Les modifications introduites dans la nouvelle version qui génèrent de tels problèmes sont appelées *modifications avec rupture* et elles sont généralement requises par des modifications apportées à la norme du langage C\+\+, aux signatures des fonctions ou à la disposition des objets en mémoire.  
  
 Pour éviter les erreurs d'exécution qui sont difficiles à détecter et diagnostiquer, nous vous recommandons de ne jamais établir de lien statique à des binaires qui ont été compilés à l'aide de différentes versions du compilateur. En outre, lorsque vous mettez à niveau un projet EXE ou DLL, veillez à mettre à niveau les bibliothèques auxquelles il est lié. Si vous utilisez des types CRT \(C Runtime\) ou STL \(Standard Template Library\), ne les transmettez pas entre des binaires \(y compris des DLL\) qui ont été compilés à l'aide de différentes versions du compilateur. Pour plus d'informations, consultez [Erreurs potentielles de passage d'objets CRT entre frontières DLL](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).  
  
 Nous vous recommandons également de ne jamais rédiger de code dépendant d'une disposition particulière pour un objet qui n'est pas une interface COM ou un objet POD. Si vous rédigez un tel code, vous devez vous assurer qu'il fonctionne après la mise à niveau. Pour plus d'informations, consultez [Portabilité aux limites ABI](../cpp/portability-at-abi-boundaries-modern-cpp.md).  
  
 Le reste de cet article décrit des modifications avec rupture spécifiques dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] et, dans cet article, les termes « nouveau comportement » ou « à présent » font référence à cette version. Les termes « ancien comportement » et « avant » font référence à Visual Studio 2013 et aux versions antérieures. Pour plus d’informations sur les modifications supplémentaires dans Visual Studio 2015 Mise à jour 1, consultez [Modifications avec rupture dans Mise à jour 1](../misc/breaking-changes-in-visual-cpp-2015-update-1.md).  
  
1.  [Modifications avec rupture du compilateur](#BK_compiler)  
  
2.  [Modifications avec rupture de la bibliothèque C Runtime \(CRT\)](#BK_CRT)  
  
3.  [Modifications avec rupture de la bibliothèque STL \(Standard Template Library\) et C\+\+ standard](#BK_STL)  
  
4.  [Modifications avec rupture MFC et ATL](#BK_MFC)  
  
5.  [Changements importants du runtime d’accès concurrentiel](#BK_ConcRT)  
  
##  <a name="BK_compiler"></a> Compilateur Visual C\+\+  
  
-   Option \/Zc:forScope\-  
  
     Options du compilateur  **\/Zc:forScope\-** est déconseillée et sera supprimée dans une version ultérieure.  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     Cette option était généralement utilisée pour autoriser du code non standard utilisant des variables de boucle après le point où, selon la norme, elles devraient être hors de portée. Elle était nécessaire uniquement en cas de compilation avec l'option \/Za, étant donné que sans \/Za, l'utilisation d'une variable de boucle for après la fin de la boucle est toujours autorisée. Si vous ne vous souciez pas de la conformité aux normes \(par exemple, si votre code n'est pas destiné à d'autres compilateurs\), vous pouvez éventuellement désactiver l'option \/Za \(ou affecter à la propriété Désactivation des extensions de langage la valeur Non\). Si vous souhaitez écrire un code portable, conforme aux normes, vous devez réécrire votre code afin qu'il soit conforme à la norme en déplaçant la déclaration de ces variables vers un point extérieur à la boucle.  
  
    ```  
    // zc_forScope.cpp // compile with: /Zc:forScope- /Za // C2065 expected int main() { // Uncomment the following line to resolve. // int i; for (int i =0; i < 1; i++) ; i = 20;   // i has already gone out of scope under /Za }  
    ```  
  
-   **\/Zg, option de compilateur**  
  
     L'option de compilateur \/Zg \(Générer des prototypes de fonction\) n'est plus disponible. Cette option de compilateur a été déconseillée précédemment.  
  
-   Vous ne pouvez plus exécuter de tests unitaires avec C\+\+\/CLI à partir de la ligne de commande avec mstest.exe. À la place, utilisez vstest.console.exe. Consultez [Options de ligne de commande VSTest.Console.exe](../Topic/VSTest.Console.exe%20command-line%20options.md).  
  
-   **mutable, mot clé**  
  
     Le spécificateur de classe de stockage `mutable` n'est plus autorisé dans les emplacements où il pouvait être compilé sans erreur auparavant. À présent, le compilateur attribue l'erreur C2071 \(classe de stockage non conforme\). Conformément à la norme, le spécificateur mutable peut être appliqué uniquement à des noms de données membres de classe. Il ne peut pas être appliqué à des noms déclarés const ou static, ni à des membres de référence.  
  
     Considérons par exemple le code suivant :  
  
    ```  
    struct S { mutable int &r; };  
    ```  
  
     Les versions précédentes du compilateur Visual C\+\+ acceptaient cela, mais le compilateur attribue désormais l'erreur suivante :  
  
    ```Output  
    erreur C2071 : 'S::r' : classe de stockage non conforme  
    ```  
  
     Pour corriger cette erreur, supprimez simplement le mot clé mutable redondant.  
  
-   **char\_16\_t et char32\_t**  
  
     Vous ne pouvez plus utiliser `char16_t` ou `char32_t` comme alias dans un typedef, car ces types sont maintenant traités comme des types intégrés. Il était courant que des utilisateurs et des auteurs de bibliothèques définissent char16\_t et char32\_t en tant qu'alias de uint16\_t et uint32\_t, respectivement.  
  
    ```  
    #include <cstdint> typedef uint16_t char16_t; //C2628 typedef uint32_t char32_t; //C2628 int main(int argc, char* argv[]) { uint16_t x = 1; uint32_t y = 2; char16_t a = x; char32_t b = y; return 0; }  
    ```  
  
     Pour mettre à jour votre code, supprimez les déclarations typedef et renommez les autres identificateurs qui entrent en conflit avec ces noms.  
  
-   **Paramètres de modèle sans type**  
  
     Du code qui implique des paramètres de modèle sans type fait à présent l'objet d'une vérification correcte de la compatibilité des types quand vous fournissez des arguments template explicites. Par exemple, le code suivant pouvait être compilé sans erreur dans les versions antérieures de Visual C\+\+.  
  
    ```  
    struct S1 { void f(int); void f(int, int); }; struct S2 { template <class C, void (C::*Function)(int) const> void f() {} }; void f() { S2 s2; s2.f<S1, &S1::f>(); }  
  
    ```  
  
     Le compilateur actuel attribue normalement une erreur, car le type de paramètre de modèle ne correspond pas à l'argument template \(le paramètre est un pointeur vers un membre const, mais la fonction f est non const\) :  
  
    ```Output  
    erreur C2893 : La spécialisation du modèle de fonction ’void S2::f(void)’ a échoué. Remarque : Avec les arguments template suivants : remarque : ’C=S1’ remarque : ’Function=S1::f’  
    ```  
  
     Pour résoudre cette erreur dans votre code, assurez\-vous que le type de l'argument template que vous utilisez correspond au type déclaré du paramètre de modèle.  
  
-   **\_\_declspec\(align\)**  
  
     Le compilateur n'accepte plus `__declspec(align)` sur les fonctions. Ceci était toujours ignoré, mais à présent cela génère une erreur du compilateur.  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     Pour résoudre ce problème, supprimez `__declspec(align)` de la déclaration de fonction. Comme cela n'avait aucun effet, la suppression ne change rien.  
  
-   **Gestion des exceptions**  
  
     Quelques modifications ont été apportées à la gestion des exceptions. Tout d'abord, les objets d'exception doivent pouvoir être copiés ou déplacés. Le code suivant pouvait être compilé dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], mais ne le peut pas dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] :  
  
    ```  
    struct S { public: S(); private: S(const S &); }; int main() { throw S(); // error }  
  
    ```  
  
     Le problème est que le constructeur de copie est privé, si bien que l'objet ne peut pas être copié comme dans le cours normal de la gestion d'une exception. La même règle s'applique quand le constructeur de copie est déclaré `explicit`.  
  
    ```  
    struct S { S(); explicit S(const S &); }; int main() { throw S(); // error }  
  
    ```  
  
     Pour mettre à jour votre code, assurez\-vous que le constructeur de copie de votre objet d'exception est public et qu'il n'est pas marqué `explicit`.  
  
     L'interception d'une exception par sa valeur exige que l'objet d'exception puisse être copié. Le code suivant pouvait être compilé dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], mais ne le peut pas dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] :  
  
    ```  
    struct B { public: B(); private: B(const B &); }; struct D : public B { }; int main() { try { } catch (D d) // error { } }  
  
    ```  
  
     Vous pouvez résoudre ce problème en remplaçant le type de paramètre pour `catch` par une référence.  
  
    ```  
    catch(D& d) { }  
    ```  
  
-   **Littéraux de chaîne suivis par des macros**  
  
     Le compilateur prend désormais en charge les littéraux définis par l'utilisateur. Par conséquent, les littéraux de chaîne suivis par des macros sans espace blanc intermédiaire sont interprétés comme des littéraux définis par l'utilisateur, qui peuvent entraîner des erreurs ou des résultats inattendus. Par exemple, dans les compilateurs précédents, le code suivant pouvait être compilé avec succès :  
  
    ```  
    #define _x "there" char* func() { return "hello"_x; } int main() { char * p = func(); return 0; }  
    ```  
  
     Le compilateur interprétait cela comme un littéral de chaîne « hello » suivi par une macro, correspondant à « there » étendu, puis les deux littéraux de chaîne étaient concaténés en un seul. Dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], le compilateur interprète cela comme un littéral défini par l'utilisateur, mais comme il n'existe aucun littéral défini par l'utilisateur correspondant \_x défini, il génère une erreur.  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     Pour résoudre ce problème, ajoutez un espace entre le littéral de chaîne et la macro.  
  
-   **Littéraux de chaîne adjacents**  
  
     Comme précédemment, en raison des modifications associées dans l'analyse des chaînes, les littéraux de chaîne adjacents \(littéraux de chaîne aux caractères larges ou étroits\) sans espace blanc étaient interprétés comme une chaîne concaténée unique dans les versions antérieures de Visual C\+\+. Dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], vous devez à présent ajouter un espace blanc entre les deux chaînes. Par exemple, le code suivant doit être modifié :  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     Ajoutez simplement un espace entre les deux chaînes.  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **Placement new et delete**  
  
     Une modification a été apportée à l'opérateur delete afin de le mettre en conformité avec la norme C\+\+14. Vous trouverez les détails relatifs au changement de normes sur la page décrivant la [libération dimensionnée C\+\+](http://isocpp.org/files/papers/n3778.html). Les modifications ajoutent une forme de l'opérateur delete global qui accepte un paramètre de taille. La modification avec rupture tient au fait que si vous utilisiez précédemment un opérateur delete avec la même signature \(pour correspondre à un opérateur placement new\), vous recevrez une erreur de compilation \(C2956, qui se produit au point où l'opérateur placement new est utilisé, étant donné qu'il s'agit de la position dans le code où le compilateur tente d'identifier un opérateur delete correspondant approprié\).  
  
     La fonction `void operator delete(void *, size_t)` était un opérateur placement delete correspondant à la fonction placement new « void \* operator new\(size\_t, size\_t\) » dans C\+\+11. Avec la désallocation dimensionnée C\+\+14, cette fonction delete est à présent une *fonction de désallocation habituelle* \(opérateur delete global\). La norme impose que si l'utilisation d'un opérateur placement new recherche une fonction delete correspondante et trouve une fonction de désallocation habituelle, le programme est incorrect.  
  
     Par exemple, supposons que votre code définit à la fois un opérateur placement new et un opérateur placement delete :  
  
    ```  
    void * operator new(std::size_t, std::size_t); void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     Le problème se produit en raison de la correspondance dans les signatures de fonction entre un opérateur placement delete que vous avez défini et le nouvel opérateur delete dimensionné global. Envisagez d'utiliser un autre type que size\_t pour n'importe quel opérateur placement new ou delete.  Notez que le type du typedef size\_t dépend du compilateur. Il s'agit d'un typedef pour unsigned int dans Visual C\+\+. Il est recommandé d'utiliser un type énuméré tel que :  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     Ensuite, modifiez votre définition de placement new et delete pour utiliser ce type comme second argument à la place de size\_t. Vous devez également mettre à jour les appels à placement new pour transmettre le nouveau type \(par exemple, en utilisant `static_cast<my_type>` pour effectuer une conversion à partir de la valeur entière\) et mettre à jour la définition de new et delete pour effectuer un cast en retour vers le type entier. Vous n'avez pas besoin d'utiliser un enum pour cela. Un type de classe avec un membre size\_t fonctionne également.  
  
     Une autre solution consiste à éliminer l'opération placement new complète. Si votre code utilise placement new pour implémenter un pool de mémoires où l'argument de positionnement est la taille de l'objet qui est alloué ou supprimé, la fonction de désallocation dimensionnée peut être appropriée pour remplacer votre propre code de pool de mémoires personnalisé, et vous pouvez vous débarrasser des fonctions de positionnement et utiliser simplement votre propre opérateur delete à deux arguments à la place des fonctions de positionnement.  
  
     Si vous ne voulez pas mettre à jour votre code immédiatement, vous pouvez revenir à l'ancien comportement en utilisant l'option de compilateur \/Zc:sizedDealloc\-. Si vous utilisez cette option, les fonctions delete à deux arguments n'existent pas et ne causeront pas de conflit avec votre opérateur placement delete.  
  
-   **Membres de données d'union**  
  
     Les membres de données d'unions ne peuvent plus posséder de types de référence. Il était possible de compiler le code suivant dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], mais il génèrait une erreur dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
    ```  
    union U1 { const int i; }; union U2 { int &i; }; union U3 { struct {int &i;}; };  
    ```  
  
     Le code précédent génère les erreurs suivantes :  
  
    ```Output  
    test.cpp(67) : erreur C2625 : ’U2::i’: membre d’union illégal ; le type ’int &’ est le type de référence test.cpp(70) : erreur C2625 : ’U3::i’: membre d’union illégal ; le type ’int &’ est le type de référence  
    ```  
  
     Pour résoudre ce problème, modifiez les types de référence en spécifiant un pointeur ou une valeur. La modification du type en pointeur nécessite des modifications dans le code qui utilise le champ union. La modification du code en valeur modifierait les données stockées dans l'union, ce qui affecte les autres champs dans la mesure où les champs dans les types d'union partagent la même mémoire. Selon la taille de la valeur, cela peut également modifier la taille de l'union.  
  
-   Les unions anonymes sont à présent plus conformes à la norme. Les versions précédentes du compilateur généraient un constructeur explicite et un destructeur pour les unions anonymes. Ceux\-ci sont supprimés dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  
  
    ```  
    struct S { S(); }; union { struct { S s; }; } u; // C2280  
    ```  
  
     Le code précédent génère l'erreur suivante dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] :  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     Pour résoudre ce problème, fournissez vos propres définitions du constructeur et\/ou du destructeur.  
  
    ```  
    struct S { // Provide a default constructor by adding an empty function body. S() {} }; union { struct { S s; }; } u;  
    ```  
  
-   **Unions avec structs anonymes**  
  
     Pour se conformer à la norme, le comportement d'exécution a changé pour les membres de structures anonymes dans les unions. Le constructeur pour les membres de structure anonymes dans une union n'est plus implicitement appelé lors de la création d'une telle union. De plus, le destructeur pour les membres de structure anonymes dans une union n'est plus implicitement appelé quand l'union passe hors de portée. Considérons le code suivant, dans lequel une union U contient une structure anonyme contenant un membre qui est une structure nommée S possèdant un destructeur.  
  
    ```  
    #include <stdio.h> struct S { S() { printf("Creating S\n"); } ~S(){ printf("Destroying S\n"); } }; union U { struct { S s; }; U() {} ~U(){} }; void f() { U u; // Destructor implicitly called here. } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
     Dans [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)], le constructeur de S est appelé quand l'union est créée, et le destructeur de S est appelé quand la pile pour la fonction f est nettoyée. Mais, dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], le constructeur et le destructeur ne sont pas appelés. Le compilateur émet un avertissement à propos de ce changement de comportement.  
  
    ```Output  
    avertissement C4587 : ’U::s’ : changement de comportement : le constructeur n’est plus appelé de manière implicite avertissement C4588 : ’U::s’ : changement de comportement : le destructeur n’est plus appelé de manière implicite  
    ```  
  
     Pour restaurer le comportement d'origine, nommez la structure anonyme. Le comportement d'exécution des structures non anonymes est le même, quelle que soit la version du compilateur.  
  
    ```  
    #include <stdio.h> struct S { S() { printf("Creating S.\n"); } ~S() { printf("Destroying S\n"); } }; union U { struct { S s; } namedStruct; U() {} ~U() {} }; void f() { U u; } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
     Sinon, essayez de déplacer le code du constructeur et du destructeur dans de nouvelles fonctions et ajoutez des appels à ces fonctions à partir du constructeur et du destructeur pour l'union.  
  
    ```  
    #include <stdio.h> struct S { void Create() { printf("Creating S.\n"); } void Destroy() { printf("Destroying S\n"); } }; union U { struct { S s; }; U() { s.Create();  } ~U() { s.Destroy(); } }; void f() { U u; } int main() { f(); char s[1024]; printf("Press any key.\n"); gets_s(s); return 0; }  
    ```  
  
-   **Résolution de modèle**  
  
     Des modifications ont été apportées à la résolution de noms pour les modèles. En C\+\+, quand vous envisagez des candidats pour la résolution d'un nom, il peut arriver qu'un ou plusieurs noms considérés comme des correspondances potentielles produisent une instanciation de modèle non valide. Ces instanciations non valides ne provoquent normalement pas d'erreurs du compilateur, un principe appelé SFINAE \(Substitution Failure Is Not An Error\).  
  
     À présent, si le principe SFINAE exige que le compilateur instancie la spécialisation d'un modèle de classe, toutes les erreurs qui surviennent au cours de ce processus sont des erreurs du compilateur. Dans les versions précédentes, le compilateur ignore de telles erreurs. Considérons par exemple le code suivant :  
  
    ```  
    #include <type_traits> template<typename T> struct S { S() = default; S(const S&); S(S&&); template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type> S(S<U>&&); }; struct D; void f1() { S<D> s1; S<D> s2(s1); } struct B { }; struct D : public B { }; void f2() { S<D> s1; S<D> s2(s1); }  
  
    ```  
  
     Si vous effectuez une compilation avec le compilateur actuel, vous obtenez l'erreur suivante :  
  
    ```Output  
    type_traits(1110) : erreur C2139 : ’D’ : une classe non définie n’est pas autorisée en tant qu’argument pour un trait de type intrinsèque du compilateur ’__is_base_of’ ..\t331.cpp(14) : remarque : voir la déclaration de ’D’ ..\t331.cpp(10) : remarque : voir la référence à l’instanciation de modèle de classe ’std::is_base_of<T,U>’ en cours de compilation avec [ T=D, U=D ]  
    ```  
  
     La raison en est qu'au point de la première invocation de is\_base\_of, la classe 'D' n'a pas encore été définie.  
  
     Dans ce cas, la correction proposée consiste à ne pas utiliser type traits tant que la classe n’a pas été définie. Si vous placez les définitions de B et D au début du fichier de code, l’erreur est résolue. Si les définitions sont dans des fichiers d'en\-tête, vérifiez l'ordre des instructions include pour les fichiers d'en\-tête afin de vous assurer que toutes les définitions de classe sont compilées avant l'utilisation des modèles problématiques.  
  
-   **Constructeurs de copie**  
  
     Dans [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] et [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)], le compilateur génère un constructeur de copie pour une classe si cette classe possède un constructeur de déplacement défini par l'utilisateur mais aucun constructeur de copie défini par l'utilisateur. Dans Dev14, ce constructeur de copie généré implicitement est également marqué « \= delete ».  
  
##  <a name="BK_CRT"></a> Bibliothèque Runtime C \(CRT\)  
  
### Modifications générales  
  
-   **Fichiers binaires refactorisés**  
  
     La bibliothèque CRT a été refactorisée en deux fichiers binaires différents, la bibliothèque Universal CRT \(ucrtbase\), qui contient la plupart des fonctionnalités standard, et une bibliothèque runtime VC \(vcruntime140\), qui contient les fonctionnalités associées au compilateur, telles que la gestion des exceptions et les intrinsèques. Si vous utilisez les paramètres de projet par défaut, cette modification n'a aucune incidence, car l'éditeur de liens utilise automatiquement les nouvelles bibliothèques par défaut. Si vous avez défini la propriété **Éditeur de liensIgnorer toutes les bibliothèques par défaut** du projet sur **Oui** ou si vous utilisez l'option \/NODEFAULTLIB de l'éditeur de liens sur la ligne de commande, vous devez mettre à jour votre liste de bibliothèques \(dans la propriété **Dépendances supplémentaires**\) pour inclure les nouvelles bibliothèques refactorisées. Remplacez l'ancienne bibliothèque CRT \(libcmt.lib, libcmtd.lib, msvcrt.lib, msvcrtd.lib\) par les bibliothèques refactorisées équivalentes. Pour chacune des deux bibliothèques refactorisées, il existe des versions statiques \(.lib\) et dynamiques \(.dll\), ainsi que des versions release \(sans suffixe\) et debug \(avec le suffixe « d »\). Les versions dynamiques ont une bibliothèque d'importation avec laquelle vous établissez une liaison. Les deux bibliothèques refactorisées sont Universal CRT, en particulier ucrtbase.dll ou .lib, ucrtbased.dll ou .lib, et la bibliothèque runtime VC, libvcruntime.lib, libvcruntime.dll, libvcruntimed.lib et libvcruntimed.dll. Consultez [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md).  
  
### \<locale.h\>  
  
-   **localeconv**  
  
     La fonction [localeconv](../c-runtime-library/reference/localeconv.md) déclarée dans locale.h fonctionne à présent correctement quand les [paramètres régionaux par thread](../parallel/multithreading-and-locales.md) sont activés. Dans les versions précédentes de la bibliothèque, cette fonction retournait les données lconv pour les paramètres régionaux globaux, et non pas pour les paramètres régionaux du thread.  
  
     Si vous utilisez les paramètres régionaux par thread, vous devez vérifier votre utilisation de localeconv pour voir si votre code suppose que les données lconv retournées s'appliquent aux paramètres régionaux globaux, et le modifier de manière appropriée.  
  
### \<math.h\>  
  
-   **Surcharges C\+\+ des fonctions mathématiques de la bibliothèque**  
  
     Dans les versions précédentes, \<math.h\> définissait certaines surcharges C\+\+ pour les fonctions mathématiques de la bibliothèque. \<cmath\> définissait les surcharges restantes, si bien que pour obtenir toutes les surcharges, il était nécessaire d'inclure l'en\-tête \<cmath\>. Cela conduisait à des problèmes de résolution de surcharge de fonction dans un code incluant uniquement \<math.h\>. À présent, toutes les surcharges C\+\+ ont été supprimées de \<math.h\> et sont désormais présentes uniquement dans \<cmath\>.  
  
     Pour résoudre les erreurs, incluez \<cmath\> pour obtenir les déclarations des fonctions qui ont été supprimées de \<math.h\>. Le tableau ci\-dessous répertorie les fonctions qui ont été déplacées.  
  
     Fonctions déplacées :  
  
    1.  double abs\(double\) et float abs\(float\)  
  
    2.  double pow\(double, int\), float pow\(float, float\), float pow\(float, int\), long double pow\(long double, long double\), long double pow\(long double, int\)  
  
    3.  versions float et long double des fonctions à virgule flottante acos, acosh, asin, asinh, atan, atanh, atan2, cbrt, ceil, copysign, cos, cosh, erf, erfc, exp, exp2, expm1, fabs, fdim, floor, fma, fmax, fmin, fmod, frexp, hypot, ilogb, ldexp, lgamma, llrint, llround, log, log10, log1p, log2, lrint, lround, modf, nearbyint, nextafter, nexttoward, remainder, remquo, rint, round, scalbln, scalbn, sin, sinh, sqrt, tan, tanh, tgamma, trunc  
  
     Si vous avez un code qui utilise abs avec un type à virgule flottante incluant uniquement l'en\-tête math.h, les versions à virgule flottante ne sont plus disponibles, si bien que l'appel, même avec un argument à virgule flottante, se traduit à présent par abs\(int\). Cela génère l'erreur :  
  
    ```Output  
    avertissement C4244 : 'argument' : conversion de 'float' en 'int', perte possible de données  
    ```  
  
     Le correctif pour cet avertissement consiste à remplacer l'appel à abs par une version à virgule flottante de abs, telle que fabs pour un argument double ou fabsf pour un argument float, ou à inclure l'en\-tête cmath et à continuer d'utiliser abs.  
  
-   **Conformité en matière de virgule flottante**  
  
     De nombreuses modifications ont été apportées à la bibliothèque mathématique pour améliorer la conformité aux normes IEEE\-754 et C11 annexe F en ce qui concerne les entrées de cas spéciaux telles que les valeurs NaN et les infinis. Par exemple, les entrées NaN silencieuses, qui étaient souvent considérées comme des erreurs dans les versions antérieures de la bibliothèque, ne sont plus traitées comme des erreurs. Consultez la [norme IEEE 754](http://grouper.ieee.org/groups/754) et l’annexe F de la [norme C11](http://www.iso-9899.info/wiki/The_Standard).  
  
     Ces modifications ne provoqueront pas d'erreurs de compilation, mais peuvent entraîner des changements de comportement des programmes \(plus conforme à la norme\).  
  
-   **FLT\_ROUNDS**  
  
     Dans Visual Studio 2013, la macro FLT\_ROUNDS s'étendait à une expression constante, ce qui était incorrect car le mode d'arrondi est configurable à l'exécution, par exemple, en appelant fesetround. La macro FLT\_ROUNDS est à présent dynamique et reflète fidèlement le mode d'arrondi actuel.  
  
### \<new\> et \<new.h\>  
  
-   **new et delete**  
  
     Dans les versions antérieures de la bibliothèque, les fonctions opérateur new et delete définies par l'implémentation étaient exportées à partir de la DLL de la bibliothèque runtime \(par exemple, msvcr120.dll\). Ces fonctions opérateur sont à présent toujours liées statiquement dans vos fichiers binaires, même si vous utilisez les DLL de la bibliothèque runtime.  
  
     Ce n'est pas une modification avec rupture pour du code natif ou mixte \(\/clr\). Toutefois, pour du code compilé en tant que [\/clr:pure](../build/reference/clr-common-language-runtime-compilation.md), cette modification peut entraîner l'échec de la compilation de votre code. Si vous compilez du code en tant que \/clr:pure, vous devrez peut\-être ajouter \#include \<new\> ou \#include \<new.h\> pour contourner les erreurs de build en raison de cette modification. Notez que \/clr:pure est déconseillé dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] et sera peut\-être supprimé dans les versions futures.  
  
### \<process.h\>  
  
-   **\_beginthread et \_beginthreadex**  
  
     Les fonctions [\_beginthread](../c-runtime-library/reference/beginthread-beginthreadex.md) et [\_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) contiennent à présent une référence au module dans lequel la procédure de thread est définie pour la durée du thread. Cela permet de garantir que les modules ne sont pas déchargés tant qu'un thread n'a pas été exécuté jusqu'à la fin.  
  
### \<stdarg.h\>  
  
-   **va\_start et types référence**  
  
     Lors de la compilation de code C\+\+, [va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) valide désormais que l'argument qui lui est transmis n'est pas de type référence. Les arguments de type référence sont interdits par la norme C\+\+.  
  
### \<stdio.h\> et \<conio.h\>  
  
-   **Les familles de fonctions printf et scanf sont maintenant définies inline.**  
  
     Les définitions de toutes les fonctions printf et scanf ont été placées inline dans \<stdio.h\>, \<conio.h\> et les autres en\-têtes CRT. Ceci est une modification avec rupture qui conduit à une erreur de l'éditeur de liens \(LNK2019, symbole externe non résolu\) pour tous les programmes ayant déclaré ces fonctions localement sans inclure les en\-têtes CRT appropriés. Si possible, vous devez mettre à jour le code pour inclure les en\-têtes CRT \(c'est\-à\-dire, ajouter \#include \<stdio.h\>\) et les fonctions inline, mais si vous ne souhaitez pas modifier votre code pour inclure ces fichiers d'en\-tête, une autre solution consiste à ajouter une bibliothèque supplémentaire à votre entrée d'éditeur de liens, legacy\_stdio\_definitions.lib.  
  
     Pour ajouter cette bibliothèque à votre entrée d'éditeur de liens dans l'environnement IDE, ouvrez le menu contextuel pour le nœud du projet, choisissez **Propriétés**, puis dans la boîte de dialogue **Propriétés du projet**, choisissez **Éditeur de liens** et modifiez l'**entrée de l'Éditeur de liens** pour ajouter legacy\_stdio\_definitions.lib à la liste séparée par des points\-virgules.  
  
     Si votre projet est lié à des bibliothèques statiques qui ont été compilées avec une version de Visual C\+\+ antérieure à 2015, l'éditeur de liens peut signaler un symbole externe non résolu. Ces erreurs peuvent référencer des définitions stdio internes pour \_iob, \_iob\_func ou des importations associées pour certaines fonctions stdio de la forme \_imp\_\*. Microsoft recommande de recompiler toutes les bibliothèques statiques avec la dernière version des bibliothèques et du compilateur Visual C\+\+ quand vous mettez à niveau un projet. Si la bibliothèque est une bibliothèque tierce dont la source n'est pas disponible, vous devez demander un fichier binaire mis à jour auprès de la tierce partie ou encapsuler votre utilisation de cette bibliothèque dans une DLL distincte que vous compilez à l'aide de l'ancienne version des bibliothèques et du compilateur Visual C\+\+.  
  
    > [!WARNING]
    >  Si vous établissez une liaison avec le Kit de développement logiciel \(SDK\) Windows 8.1 ou version antérieure, vous pouvez rencontrer ces erreurs de symbole externe non résolues. Dans ce cas, vous devez résoudre l'erreur en ajoutant legacy\_stdio\_definitions.lib à l'entrée de l'éditeur de liens, comme décrit précédemment.  
  
     Pour résoudre les erreurs de symbole non résolues, vous pouvez essayer d'utiliser [dumpbin.exe](../build/reference/dumpbin-reference.md) pour examiner les symboles définis dans un fichier binaire. Essayez d'utiliser la ligne de commande ci\-dessous pour afficher les symboles définis dans une bibliothèque.  
  
    ```  
    dumpbin.exe /LINKERMEMBER somelibrary.lib  
    ```  
  
-   **gets et \_getws**  
  
     Les fonctions [gets](../c-runtime-library/gets-getws.md) et [\_getws](../c-runtime-library/gets-getws.md) ont été supprimées. La fonction gets a été supprimée de la Bibliothèque standard du C dans C11, car elle ne peut pas être utilisée en toute sécurité. La fonction \_getws était une extension Microsoft équivalente à gets, mais pour les chaînes étendues. Comme alternatives à ces fonctions, envisagez d'utiliser [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [gets\_s](../c-runtime-library/reference/gets-s-getws-s.md) et [\_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
-   **\_cgets et \_cgetws**  
  
     Les fonctions [\_cgets](../c-runtime-library/cgets-cgetws.md) et [\_cgetws](../c-runtime-library/cgets-cgetws.md) ont été supprimées. Comme alternatives à ces fonctions, envisagez d'utiliser [\_cgets\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md) et [\_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
-   **Formatage de valeurs NaN et infinies**  
  
     Dans les versions précédentes, les valeurs infinies et NaN étaient formatées à l'aide d'un ensemble de chaînes de sentinelles spécifiques à Visual C\+\+.  
  
    -   Infinity: 1.\#INF  
  
    -   Quiet NaN: 1.\#QNAN  
  
    -   Signaling NaN: 1.\#SNAN  
  
    -   Indefinite NaN: 1.\#IND  
  
     Toutes ces chaînes pouvaient être précédées par un signe et mises en forme légèrement différemment en fonction de la précision et de la largeur du champ \(parfois avec des effets inhabituels, par exemple : printf\("%.2f\\n", INFINITY\) affichait 1.\#J, car \#INF était « arrondi » avec une précision de 2 chiffres\). C99 a introduit de nouvelles spécifications sur la façon dont les valeurs infinies et NaN devaient être formatées. À présent, l'implémentation de Visual C\+\+ est conforme à ces spécifications. Les nouvelles chaînes sont :  
  
    -   Infinity: inf  
  
    -   Quiet NaN: nan  
  
    -   Signaling NaN: nan\(snan\)  
  
    -   Indefinite NaN:nan\(ind\)  
  
     Elles peuvent toutes être précédées d'un signe. Si un spécificateur de format majuscule est utilisé \(%F au lieu de %f\), les chaînes apparaissent en majuscules \(INF au lieu de inf\), comme cela est requis.  
  
     Les fonctions [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) ont été modifiées pour analyser ces nouvelles chaînes, afin que ces chaînes effectuent un aller\-retour via printf et scanf.  
  
-   **Formatage et analyse avec virgule flottante**  
  
     De nouveaux algorithmes de formatage et d'analyse de virgule flottante ont été introduits pour améliorer l'exactitude. Cette modification affecte les familles de fonctions [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) et [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), ainsi que des fonctions telles que [strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md).  
  
     Les anciens algorithmes de formatage généraient un nombre limité de chiffres, puis remplissaient les emplacements décimaux restants par des zéros. Cela est généralement suffisant pour générer des chaînes susceptibles de revenir à la valeur à virgule flottante d'origine, mais cette solution n'est pas idéale si vous souhaitez la valeur exacte \(ou sa représentation décimale la plus proche\). Les nouveaux algorithmes de formatage génèrent autant de chiffres que cela est nécessaire pour représenter la valeur \(ou pour satisfaire à la précision spécifiée\). Comme exemple illustrant cette amélioration, considérons les résultats obtenus en affichant une grande puissance de deux :  
  
    ```  
    printf("%.0f\n", pow(2.0, 80))  
  
    ```  
  
    ```Output  
        Ancien :  1208925819614629200000000    Nouveau :  1208925819614629174706176  
    ```  
  
     Les anciens algorithmes d'analyse prenaient en compte un maximum de 17 chiffres significatifs dans la chaîne d'entrée et ignoraient les chiffres restants. Cela est suffisant pour générer une approximation très proche de la valeur représentée par la chaîne et le résultat est généralement très proche du résultat correctement arrondi. La nouvelle implémentation prend en compte tous les chiffres présents et génère le résultat correctement arrondi pour toutes les entrées \(jusqu'à 768 chiffres\). En outre, ces fonctions respectent désormais le mode d'arrondi \(contrôlable via fesetround\).  Il s'agit potentiellement d'un comportement de rupture, car les fonctions peuvent générer des résultats différents. Les nouveaux résultats sont toujours plus exacts que les anciens.  
  
-   **Analyse de virgule flottante de valeurs hexadécimales et infinies\/NaN**  
  
     Les algorithmes d'analyse de virgule flottante analyseront à présent les chaînes hexadécimales à virgule flottante \(telles que celles générées par les spécificateurs de format printf %a et %A\) et toutes les chaînes infinies et NaN générées par les fonctions printf, comme décrit ci\-dessus.  
  
-   **Remplissage à l'aide de zéros de %A et %a**  
  
     Les spécificateurs de format %a et %A formatent un nombre à virgule flottante sous la forme d'une mantisse hexadécimale et d'un exposant binaire. Dans les versions antérieures, les fonctions printf remplissaient à l'aide de zéro les chaînes, ce qui était incorrect. Par exemple, printf\("%07.0a\\n", 1,0\) affichait 00x1p\+0, alors que le résultat correct est 0x01p\+0. Ce problème a été corrigé.  
  
-   **Précision de %A et %a**  
  
     La précision par défaut des spécificateurs de format %A et %a était de 6 dans les versions antérieures de la bibliothèque. La précision par défaut est désormais de 13 pour être conforme à la norme du C.  
  
     Il s'agit d'un changement de comportement d'exécution dans la sortie de n'importe quelle fonction qui utilise une chaîne de format avec %A ou %a. Selon l'ancien comportement, la sortie utilisant le spécificateur %A peut être « 1,1A2B3Cp\+111 ». À présent, la sortie pour la même valeur est « 1,1A2B3C4D5E6F7p\+111 ». Pour obtenir l'ancien comportement, vous pouvez spécifier la précision, par exemple, %.6A. Consultez [Spécifications de précision](../c-runtime-library/precision-specification.md).  
  
-   **Spécificateur %F**  
  
     Le spécificateur de format\/conversion %F est maintenant pris en charge. Il est fonctionnellement équivalent au spécificateur de format %f, si ce n'est que les valeurs infinies et NaN sont formatées au moyen de lettres majuscules.  
  
     Dans les versions précédentes, l'implémentation analysait F et N en tant que modificateurs de longueur. Ce comportement datait du temps des espaces d'adressage segmentés : ces modificateurs de longueur servaient à indiquer des pointeurs proches et lointains, respectivement, comme dans %Fp ou %Ns. Ce comportement a été supprimé. %F est désormais traité comme le spécificateur de format %F. Si vous rencontrez %N, il est maintenant traité comme un paramètre non valide.  
  
-   **Formatage des exposants**  
  
     Les spécificateurs de format %e et %E formatent un nombre à virgule flottante sous la forme d'une mantisse décimale et d'un exposant. Les spécificateurs de format %g et %G formatent également les nombres sous cette forme, dans certains cas. Dans les versions précédentes, le CRT générait toujours des chaînes avec des exposants à trois chiffres. Par exemple, printf\("%e\\n", 1,0\) affichait 1,000000e\+000. Cela était incorrect : le langage C requiert que si l'exposant peut être représenté à l'aide d'un ou de deux chiffres, seulement deux chiffres doivent être affichés.  
  
     Dans Visual Studio 2005, un commutateur de conformité globale a été ajouté : [\_set\_output\_format](../c-runtime-library/set-output-format.md). Un programme peut appeler cette fonction avec l'argument \_TWO\_DIGIT\_EXPONENT pour permettre un affichage d'exposant conforme. Le comportement par défaut a été remplacé par le mode d'affichage d'exposant conforme aux normes.  
  
-   **Validation des chaînes de format**  
  
     Dans les versions précédentes, les fonctions printf et scanf acceptaient silencieusement de nombreuses chaînes de format non valides, parfois avec des effets inhabituels. Par exemple, %hlhlhld était traité comme %d. Toutes les chaînes de format non valides sont désormais traitées comme des paramètres non valides.  
  
-   **Validation des chaînes de mode fopen**  
  
     Dans les versions précédentes, la famille fopen de fonctions acceptait silencieusement certaines chaînes de mode non valides \(par exemple r\+b\+\). Les chaînes de mode non valides sont désormais détectées et traitées comme des paramètres non valides.  
  
-   **Mode \_O\_U8TEXT**  
  
     La fonction [\_setmode](../c-runtime-library/reference/setmode.md) signale désormais correctement le mode pour les flux ouverts en mode \_O\_U8TEXT. Dans les versions précédentes de la bibliothèque, elle signalait ces flux de données comme étant ouverts dans \_O\_WTEXT.  
  
     Il s'agit d'une modification avec rupture si votre code interprète le mode \_O\_WTEXT pour des flux dont l'encodage est UTF\-8. Si votre application ne prend pas en charge UTF\_8, envisagez d'ajouter la prise en charge pour cet encodage de plus en plus courant.  
  
-   **snprintf et vsnprintf**  
  
     Les fonctions [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) et [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) sont à présent implémentées. Du code plus ancien fournissait souvent des versions macro de définitions de ces fonctions, car elles n'étaient pas implémentées par la bibliothèque CRT, mais celles\-ci ne sont plus nécessaires dans les versions plus récentes. Si [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) ou [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) est défini comme macro avant l'inclusion de \<stdio.h\>, la compilation échoue désormais avec une erreur qui indique où la macro a été définie.  
  
     Normalement, le correctif de ce problème consiste à supprimer toutes les déclarations de snprintf ou vsnprintf dans le code utilisateur.  
  
-   **tmpnam génère des noms de fichiers utilisables**  
  
     Dans les versions précédentes, les fonctions tmpnam et tmpnam\_s généraient des noms de fichiers à la racine du lecteur \(par exemple, \\sd3c.\). Ces fonctions génèrent désormais des chemins d'accès de noms de fichiers utilisables dans un répertoire temporaire.  
  
-   **Encapsulation FILE**  
  
     Dans les versions précédentes, le type FILE était complètement défini dans \<stdio.h\>, si bien qu'il était possible pour le code utilisateur d'accéder à un type FILE et de modifier ses éléments internes. La bibliothèque stdio a été modifiée pour masquer les détails d'implémentation. Dans ce cadre, le type FILE tel que défini dans \<stdio.h\> est désormais un type opaque et ses membres sont inaccessibles de l'extérieur de la bibliothèque CRT elle\-même.  
  
-   **\_outp et \_inp**  
  
     Les fonctions [\_outp](../c-runtime-library/outp-outpw-outpd.md), [\_outpw](../c-runtime-library/outp-outpw-outpd.md), [\_outpd](../c-runtime-library/outp-outpw-outpd.md), [\_inp](../c-runtime-library/inp-inpw-inpd.md), [\_inpw](../c-runtime-library/inp-inpw-inpd.md) et [\_inpd](../c-runtime-library/inp-inpw-inpd.md) ont été supprimées.  
  
### \<stdlib.h\>, \<malloc.h\> et \<sys\/stat.h\>  
  
-   **strtof et wcstof**  
  
     Les fonctions strtof et wcstof n'ont pas pu affecter la valeur ERANGE à errno quand la valeur n'était pas représentable en tant que valeur float. Ce problème a été corrigé. \(Notez que cette erreur était spécifique à ces deux fonctions ; les fonctions strtod, wcstod, strtold et wcstold n'étaient pas affectées\). Il s'agit d'une modification avec rupture à l'exécution.  
  
-   **Fonctions d'allocation alignée**  
  
     Dans les versions antérieures, les fonctions d’allocation alignée \(\_aligned\_malloc, \_aligned\_offset\_malloc, etc.\) acceptaient silencieusement les demandes pour un bloc avec un alignement de 0. L'alignement demandé doit être une puissance de deux, ce que zéro n'est pas. Ce problème a été résolu et un alignement demandé de 0 est désormais traité comme un paramètre non valide. Il s'agit d'une modification avec rupture à l'exécution.  
  
-   **Fonctions de segment de mémoire**  
  
     Les fonctions \_heapadd, \_heapset et \_heapused ont été supprimées. Ces fonctions ne fonctionnaient plus depuis que la bibliothèque CRT a été mise à jour pour utiliser le segment de mémoire de Windows.  
  
-   **smallheap**  
  
     L'option de liaison smalheap a été supprimée. Consultez [Options de lien](../c-runtime-library/link-options.md).  
  
### \<string.h\>  
  
-   **wcstok**  
  
     La signature de la fonction wcstok a été modifiée pour correspondre à ce qui est requis par la norme du C. Dans les versions précédentes de la bibliothèque, la signature de cette fonction était :  
  
    ```  
    wchar_t* wcstok(wchar_t*, wchar_t const*)  
    ```  
  
     Elle utilisait un contexte par thread interne pour suivre l'état entre les appels, comme c'est le cas pour strtok. La fonction a désormais la signature wchar\_t\* wcstok\(wchar\_t\*, wchar\_t const\*, wchar\_t\*\*\) et exige que l'appelant passe le contexte à la fonction comme troisième argument.  
  
     Une nouvelle fonction \_wcstok a été ajoutée avec l'ancienne signature pour faciliter le portage. Quand vous compilez du code C\+\+, il existe également une surcharge inline de wcstok qui possède l'ancienne signature. Cette surcharge est déclarée comme déconseillée. Dans le code C, vous pouvez définir \_CRT\_NON\_CONFORMING\_WCSTOK pour que \_wcstok soit utilisé à la place de wcstok.  
  
### \<time.h\>  
  
-   **horloge**  
  
     Dans les versions précédentes, la fonction [clock](../c-runtime-library/reference/clock.md) était implémentée à l’aide de l’API Windows [GetSystemTimeAsFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724397.aspx). Avec cette implémentation, la fonction clock était sensible à l'heure système et n'était donc pas nécessairement unitone. La fonction clock a été réimplémentée en tant que [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx). Elle est désormais monotone.  
  
-   **fstat et \_utime**  
  
     Dans les versions précédentes, les fonctions [\_stat](../c-runtime-library/reference/stat-functions.md), [fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md) et [\_utime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) géraient l'heure d'été de façon incorrecte. Avant Visual Studio 2013, toutes ces fonctions ajustaient de façon incorrecte les heures à l'heure d'hiver comme si les heures d'été étaient prises en compte.  
  
     Dans Visual Studio 2013, le problème a été résolu dans la famille de fonctions \_stat, mais des problèmes similaires dans les familles de fonctions fstat et \_utime n'étaient pas résolus. Cela a conduit à des problèmes en raison de l'incohérence entre les fonctions. Des corrections ont été apportées aux familles de fonctions fstat et \_utime, de sorte que toutes ces fonctions gèrent maintenant l'heure d'été de façon correcte et cohérente.  
  
-   **asctime**  
  
     Dans les versions précédentes, la fonction [asctime](../c-runtime-library/reference/asctime-wasctime.md) complétait les jours à un chiffre avec un zéro non significatif. Exemple : Ven 06 juin 08:00:00 2014. La spécification impose que ces jours soient complétés par un espace à gauche, par exemple Ven 6 juin 08:00:00 2014. Ce problème a été corrigé.  
  
-   **strftime et wcsftime**  
  
     Les fonctions strftime et wcsftime prennent désormais en charge les spécificateurs de format %C, %D, %e, %F, %g, %G, %h, %n, %r, %R, %t, %T, %u et %V. En outre, les modificateurs E et O sont analysés mais ignorés.  
  
     Le spécificateur de format %c est spécifié comme générant une « représentation appropriée de date et heure » pour les paramètres régionaux actuels. Dans les paramètres régionaux C, cette représentation doit être identique à %a %b %e %T %Y. Il s'agit de la même forme que celle produite par asctime. Dans les versions précédentes, le spécificateur de format %c formatait de façon incorrecte les heures à l'aide d'une représentation MM\/DD\/YY HH:MM:SS. Ce problème a été corrigé.  
  
-   **timespec et TIME\_UTC**  
  
     L'en\-tête \<time.h\> définit à présent le type timespec et la fonction timespec\_get issus de la norme C11. En outre, la macro TIME\_UTC, à utiliser avec la fonction timespec\_get, est maintenant définie. Il s'agit d'une modification avec rupture pour un code qui possède une définition en conflit pour l'un de ces éléments.  
  
-   **CLOCKS\_PER\_SEC**  
  
     La macro CLOCKS\_PER\_SEC s'étend désormais à un entier de type clock\_t, comme cela est requis par le langage C.  
  
###  <a name="BK_STL"></a> Bibliothèque STL \(Standard Template Library\)  
 Pour activer les nouvelles optimisations et vérifications de débogage, l'implémentation Visual Studio de la bibliothèque C\+\+ standard interrompt intentionnellement la compatibilité binaire d'une version à la suivante. Par conséquent, lorsque la bibliothèque C\+\+ standard est utilisée, les fichiers objets et les bibliothèques statiques qui sont compilés à l'aide de différentes versions ne peuvent pas être combinés en un seul binaire \(EXE ou DLL\), et les objets de la bibliothèque C\+\+ standard ne peuvent pas être transmis entre des binaires compilés à l'aide de différentes versions. Une telle combinaison entraîne des erreurs de l'éditeur de liens concernant des incompatibilités \_MSC\_VER. \(\_MSC\_VER est la macro contenant la version majeure du compilateur. Par exemple, 1800 pour Visual Studio 2013.\) Cette vérification ne peut pas détecter les combinaisons de DLL et ne peut pas détecter les combinaisons impliquant Visual C\+\+ 2008 ou version antérieure.  
  
-   **Fichiers include STL**  
  
     Certaines modifications ont été apportées à la structure include dans les en\-têtes STL. Les en\-têtes STL sont autorisés à s'inclure mutuellement de façons non spécifiées. En général, vous devez écrire votre code afin qu'il inclue soigneusement tous les en\-têtes dont il a besoin conformément à la norme C\+\+ et ne s'appuie pas sur quels en\-têtes STL incluent quels autres en\-têtes STL. Cela rend le code portable entre les versions et les plateformes. Au moins deux modifications d'en\-tête dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] affectent le code utilisateur. Tout d'abord, \<string\> n'inclut plus \<iterator\>. Deuxièmement, \<tuple\> déclare maintenant std::array sans inclure tous les \<array\>, ce qui peut endommager le code via la combinaison suivante de constructions de code : votre code possède une variable nommée « array », vous avez une directive using « using namespace std; » et vous incluez un en\-tête STL \(tel que \<functional\>\) qui inclut \<tuple\>, qui déclare maintenant std::array.  
  
-   **steady\_clock**  
  
     L'implémentation \<chrono\> de [steady\_clock](../standard-library/steady-clock-struct.md) a changé pour satisfaire les exigences de la norme C\+\+ en matière de stabilité et d'unitonicité. steady\_clock est désormais basé sur [QueryPerformanceCounter](https://msdn.microsoft.com/library/windows/desktop/ms644904.aspx), et high\_resolution\_clock est désormais un typedef pour steady\_clock. Par conséquent, dans Visual C\+\+, steady\_clock::time\_point est désormais un typedef pour chrono::time\_point\<steady\_clock\>. Toutefois, cela n'est pas nécessairement le cas pour d'autres implémentations.  
  
-   **allocateurs et const**  
  
     Nous avons à présent besoin de comparaisons d'égalité\/inégalité d'allocateurs pour accepter des arguments const des deux côtés.  Si vos allocateurs définissent ces opérateurs comme suit :  
  
    ```  
    bool operator==(const MyAlloc& other)  
    ```  
  
     Vous devez les mettre à jour pour les déclarer en tant que membres const.  
  
    ```  
    bool operator==(const MyAlloc& other) const  
    ```  
  
-   **Éléments const**  
  
     La norme C\+\+ a toujours interdit les conteneurs d'éléments const \(tels que vector\<const T\> ou set\<const T\>\). Visual C\+\+ 2013 et les versions antérieures acceptaient ces conteneurs. Dans la version actuelle, la compilation de ces conteneurs échoue.  
  
-   **std::allocator::deallocate**  
  
     Dans Visual C\+\+ 2013 et les versions antérieures, std::allocator::deallocate\(p, n\) ignorait l'argument passé pour n.  La norme C\+\+ a toujours nécessité que n soit égal à la valeur passée comme premier argument à l'appel d'allocate qui retournait p. Toutefois, dans la version actuelle, la valeur de n est inspectée. Un code qui transmet des arguments pour n qui diffèrent de ce que la norme requiert peut se bloquer lors de l'exécution.  
  
-   **hash\_map et hash\_set**  
  
     Les fichiers d'en\-tête non standard hash\_map et hash\_set sont déconseillés dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] et seront supprimés dans une version ultérieure. Utilisez unordered\_map et unordered\_set à la place.  
  
-   **comparateurs et operator\(\)**  
  
     Les conteneurs associatifs \(famille \<map\>\) exigent que leurs comparateurs possèdent des opérateurs d'appel de fonction pouvant être appelée par const. À présent, la compilation du code suivant dans une déclaration de classe de comparateur échoue :  
  
    ```  
    bool operator()(const X& a, const X& b)  
    ```  
  
     Pour résoudre cette erreur, remplacez la déclaration de fonction par :  
  
    ```  
    bool operator()(const X& a, const X& b) const  
    ```  
  
-   **caractéristiques de type**  
  
     Les anciens noms des caractéristiques de type issues d'une version antérieure du projet de norme C\+\+ ont été supprimés. Ils ont été modifiés dans C\+\+11 et ont été mis à jour pour donner les valeurs C\+\+11 dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]. Le tableau ci\-dessous répertorie les anciens noms et les nouveaux.  
  
    |Ancien nom|Nouveau nom|  
    |----------------|-----------------|  
    |add\_reference|add\_lvalue\_reference|  
    |has\_default\_constructor|is\_default\_constructible|  
    |has\_copy\_constructor|is\_copy\_constructible|  
    |has\_move\_constructor|is\_move\_constructible|  
    |has\_nothrow\_constructor|is\_nothrow\_default\_constructible|  
    |has\_nothrow\_default\_constructor|is\_nothrow\_default\_constructible|  
    |has\_nothrow\_copy|is\_nothrow\_copy\_constructible|  
    |has\_nothrow\_copy\_constructor|is\_nothrow\_copy\_constructible|  
    |has\_nothrow\_move\_constructor|is\_nothrow\_move\_constructible|  
    |has\_nothrow\_assign|is\_nothrow\_copy\_assignable|  
    |has\_nothrow\_copy\_assign|is\_nothrow\_copy\_assignable|  
    |has\_nothrow\_move\_assign|is\_nothrow\_move\_assignable|  
    |has\_trivial\_constructor|is\_trivially\_default\_constructible|  
    |has\_trivial\_default\_constructor|is\_trivially\_default\_constructible|  
    |has\_trivial\_copy|is\_trivially\_copy\_constructible|  
    |has\_trivial\_move\_constructor|is\_trivially\_move\_constructible|  
    |has\_trivial\_assign|is\_trivially\_copy\_assignable|  
    |has\_trivial\_move\_assign|is\_trivially\_move\_assignable|  
    |has\_trivial\_destructor|is\_trivially\_destructible|  
  
-   **stratégies launch::any et launch::sync**  
  
     Les stratégies non standard launch::any et launch::sync ont été supprimées. À la place, pour launch::any, utilisez launch:async &#124; launch:deferred. Pour launch::sync, utilisez launch::deferred. Consultez [launch, énumération](../Topic/launch%20Enumeration.md).  
  
###  <a name="BK_MFC"></a> MFC et ATL  
  
-   **Microsoft Foundation Classes \(MFC\)** n'est plus inclus dans une installation « Par défaut » de Visual Studio en raison de sa grande taille. Pour installer MFC, choisissez l'option d'installation Personnalisée dans le programme d'installation de Visual Studio 2015. Si Visual Studio 2015 est déjà installé, vous pouvez installer MFC en réexécutant le programme d'installation de Visual Studio, en choisissant l'option d'installation Personnalisée et en choisissant Microsoft Foundation Classes. Vous pouvez réexécuter le programme d'installation de Visual Studio à partir du Panneau de configuration, Programmes et fonctionnalités, ou à partir du support d'installation.  
  
     Le package redistribuable Visual C\+\+ inclut toujours cette bibliothèque.  
  
###  <a name="BK_ConcRT"></a> Concurrency Runtime  
  
-   **Macro Yield de Windows.h en conflit avec concurrency::Context::Yield**  
  
     Le runtime d'accès concurrentiel utilisait précédemment \#undef pour annuler la définition de la macro Yield pour éviter les conflits entre la macro Yield définie dans Windows.h et la fonction concurrency::Context::Yield. Ce \#undef a été supprimé et un nouvel appel d'API équivalent non conflictuel [concurrency::Context::YieldExecution](../Topic/Context::YieldExecution%20Method.md) a été ajouté. Pour contourner les conflits avec Yield, vous pouvez mettre à jour votre code pour appeler à la place la fonction YieldExecution ou mettre entre parenthèses le nom de la fonction Yield sur les sites d'appel, comme dans l'exemple suivant :  
  
    ```  
    (concurrency::Context::Yield)();  
    ```  
  
## Voir aussi  
 [Prise en main](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md)   
 [Changements importants dans Visual C\+\+ 2013](https://msdn.microsoft.com/library/hh409293.aspx)