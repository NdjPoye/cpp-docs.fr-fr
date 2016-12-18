---
title: "Fichiers hint | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cpp.hint"
  - "vc.hint.file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichier d'arrêt"
  - "cpp.hint"
  - "fichier hint"
  - "cpp.stop"
  - "affichage de classes, fichier hint"
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers hint
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un *fichier hint* aident le Visual Studio à l’environnement de développement intégré (IDE) d’interpréter des identificateurs de Visual C++, tels que les noms de fonctions et macros. Lorsque vous ouvrez un projet Visual C++, l’IDE *système analyse* analyse le code dans chaque fichier source dans le projet et recueille des informations sur chaque identificateur. L’IDE utilise ces informations pour prendre en charge des fonctionnalités telles que la **affichage de classes** navigateur et le **barre de Navigation**.  
  
 Le système d’analyse qui a été introduit dans [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)], comprend la syntaxe de C/C++, mais peut mal interpréter une instruction contenant une macro. L’instruction peut être mal interprétée si la macro, le code source soit incorrecte comme écrite. L’instruction peut devenir correcte lorsque le code source est compilé et que le préprocesseur remplace le [macro identificateur](../preprocessor/hash-define-directive-c-cpp.md) avec sa définition. Le système d’analyse fonctionne sans avoir à créer le projet, car il utilise des fichiers hint pour interpréter les macros. Par conséquent, une navigation fonctionnalité comme **affichage de classes** est immédiatement disponible.  
  
 Un fichier hint contient personnalisables *indicateurs*, qui ont la même syntaxe que les définitions de macros C/C++. Visual C++ inclut un fichier hint intégré qui est suffisant pour la plupart des projets, mais vous pouvez créer vos propres fichiers hint pour améliorer la manière dont Visual Studio gère les identificateurs.  
  
> [!IMPORTANT]
>  Si vous modifiez ou ajoutez un fichier de l’indicateur, vous devez supprimer le fichier .sdf et/ou le fichier VC.db dans la solution afin que les modifications prennent effet.  
  
## <a name="scenario"></a>Scénario  
 Partent du principe que le code suivant est un fichier source que vous examinez avec le **affichage de classes** navigateur. Le `STDMETHOD` macro déclare une méthode nommée `myMethod` qui prend un paramètre et retourne un pointeur vers un **HRESULT**.  
  
```  
// Source code file.  
STDMETHOD(myMethod)(int parameter1);  
```  
  
 Les définitions de macros suivantes se trouvent dans un fichier d’en-tête distinct.  
  
```  
// Header file.  
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)  
#define STDMETHODCALLTYPE __stdcall  
#define HRESULT void*  
```  
  
 Le système d’analyse ne peut pas interpréter le code source, car une fonction appelée STDMETHOD semble être déclarée, et cette déclaration est syntaxiquement incorrecte, car il contient deux listes de paramètres. Le système d’analyse n’ouvre pas le fichier d’en-tête pour découvrir les définitions pour les `STDMETHOD`, `STDMETHODCALLTYPE`, et `HRESULT` macros. Étant donné que le système d’analyse ne peut pas interpréter le `STDMETHOD` macro, il ignore toute l’instruction et poursuit l’analyse.  
  
 Le système d’analyse n’utilise pas les fichiers d’en-tête parce que votre projet peut dépendre d’un ou plusieurs fichiers d’en-tête importants. Si un fichier d’en-tête est modifié, le système d’analyse devrez réexaminer tous les fichiers d’en-tête dans votre projet, ce qui ralentit les performances de l’IDE. En revanche, le système d’analyse utilise des indications qui spécifient comment gérer les `STDMETHOD`, `STDMETHODCALLTYPE`, et `HRESULT` macros.  
  
 Comment savez-vous que vous avez besoin d’un indicateur ? Et si vous avez besoin d’une indication, quel type devez-vous créer ? Saurez qu’une indication est nécessaire si l’affichage d’un identificateur de **affichage de classes** n’est pas cohérente avec la vue dans la **éditeur**. Par exemple, **affichage de classes** peut ne pas afficher un membre de classe dont vous savez qu’il existe, ou le nom du membre est incorrect. Pour plus d’informations sur les types d’indications permettant de résoudre les problèmes courants, consultez les les Macros Require A Hint ? section plus loin dans cette rubrique.  
  
## <a name="architecture"></a>Architecture  
 Fichiers hint concernent les répertoires physiques, pas les répertoires logiques décrits dans **l’Explorateur de solutions**. Vous n’avez pas à ajouter un fichier hint à votre projet pour le fichier hint ait un effet. Le système d’analyse utilise des fichiers hint uniquement lorsqu’il analyse les fichiers sources.  
  
 Chaque fichier hint est appelé **cpp.hint**. Par conséquent, plusieurs répertoires peuvent contenir un fichier hint, mais seul fichier hint peut se produire dans un répertoire particulier.  
  
 Votre projet peut être affecté par zéro ou plusieurs fichiers hint. S’il n’existe aucun fichier hint, le système d’analyse utilise des techniques de récupération d’erreur à ignorer le code source indéchiffrable. Dans le cas contraire, le système d’analyse utilise la stratégie suivante pour rechercher et rassembler des indications.  
  
### <a name="search-order"></a>Ordre de recherche  
 Le système d’analyse recherche les répertoires de fichiers hint dans l’ordre suivant.  
  
-   Le répertoire qui contient le package d’installation pour Visual C++ (**vcpackages**). Ce répertoire contient un fichier hint intégré qui décrit les symboles dans les fichiers systèmes fréquemment utilisés, tels que **windows.h**. Par conséquent, votre projet hérite automatiquement de la plupart des indications dont il a besoin.  
  
-   Le chemin d’accès du répertoire racine d’un fichier source dans le répertoire qui contient le fichier source lui-même. Dans un projet Visual C++ classique, le répertoire racine contient le fichier solution ou projet.  
  
     L’exception à cette règle est si un *fichiers* se trouve dans le chemin d’accès au fichier source. Un fichier de mots vides offre un contrôle supplémentaire sur l’ordre de recherche et est un fichier nommé **cpp.stop**. Au lieu de démarrer à partir du répertoire racine, le système d’analyse recherche à partir du répertoire qui contient les fichiers dans le répertoire qui contient le fichier source. Dans un projet classique, il est inutile un fichier de mots vides.  
  
### <a name="hint-gathering"></a>Regroupement des indications  
 Un fichier hint contient zéro ou plusieurs *indicateurs*. Un indicateur est défini ou supprimé comme une macro C/C++. Autrement dit, la `#define` directive de préprocesseur crée ou redéfinit une indication et le `#undef` la supprime.  
  
 Le système d’analyse ouvre chaque fichier hint dans l’ordre de recherche décrit précédemment, regroupe les indications de chaque fichier dans un ensemble de *indications effectives*, puis utilise ces indications effectives pour interpréter les identificateurs dans votre code.  
  
 Le système d’analyse utilise les règles suivantes pour rassembler des indications.  
  
-   Si la nouvelle indication spécifie un nom qui n’est pas déjà défini, l’ajoute le nom aux indications effectives.  
  
-   Si la nouvelle indication spécifie un nom qui est déjà défini, elle redéfinit l’indication existante.  
  
-   Si la nouvelle indication est une `#undef` directive qui spécifie une indication effective existante, elle supprime l’indication existante.  
  
 La première règle signifie que les indications effectives sont héritées de fichiers hint précédemment ouverts. Les deux dernières règles signifient que les indicateurs qui se produisent ultérieurement dans l’ordre de recherche peuvent remplacer des indications qui se sont produites précédemment. Par exemple, vous pouvez remplacer des indications précédentes si vous créez un fichier hint dans le répertoire qui contient un fichier source.  
  
 Pour une description de la collecte des indicateurs, consultez la `Example` plus loin dans cette rubrique.  
  
### <a name="syntax"></a>Syntaxe  
 Indicateurs sont créées et supprimées avec la même syntaxe que les directives de préprocesseur qui créent et suppriment des macros. En fait, le système d’analyse utilise le préprocesseur C/C++ pour évaluer les indications. Pour plus d’informations sur les directives de préprocesseur, consultez la rubrique [#define, Directive (C/C++)](../preprocessor/hash-define-directive-c-cpp.md) et [#undef Directive (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md).  
  
 Les seuls éléments syntaxiques inhabituels sont les `@<`, `@=`, et `@>` les chaînes de remplacement. Fichier hint les chaînes de remplacement spécifiques sont utilisés uniquement avec *carte* macros. Un mappage est un ensemble de macros qui lient des données, des fonctions ou des événements à d’autres données, fonctions ou gestionnaires d’événements. Par exemple, `MFC` utilise pour créer des mappages [tables des messages](../mfc/reference/message-maps-mfc.md), et `ATL` utilise des mappages pour créer [mappe l’objet](../atl/reference/object-map-macros.md). Les chaînes de remplacement de fichiers hint indiquent les éléments de début, intermédiaires et de fin d’un mappage. Uniquement le nom d’une macro de mappage est significatif. Par conséquent, chaque chaîne de remplacement masque intentionnellement l’implémentation de la macro.  
  
 Indicateurs d’utilisent la syntaxe suivante.  
  
|Syntaxe|Signification|  
|------------|-------------|  
|`#define` *-nom de l’indicateur* *chaîne de remplacement*<br /><br /> `#define` *-nom de l’indicateur* `(` *paramètre*, ...`)`*chaîne de remplacement*|Directive de préprocesseur qui définit une nouvelle indication ou redéfinit une indication existante. Après la directive, le préprocesseur remplace chaque occurrence de *-nom de l’indicateur* dans le code source avec *-chaîne de remplacement*.<br /><br /> La deuxième forme de syntaxe définit une indication de type fonction. Si une indication de type fonction se produit dans le code source, le préprocesseur remplace tout d’abord chaque occurrence de *paramètre* dans *-chaîne de remplacement* avec l’argument correspondant dans le code source, puis remplace *-nom de l’indicateur* avec *-chaîne de remplacement*.|  
|`@<`|Fichier hint spécifique *-chaîne de remplacement* qui indique le début d’un jeu d’éléments de mappage.|  
|`@=`|Fichier hint spécifique *-chaîne de remplacement* qui indique un élément de mappage intermédiaire. Une carte peut avoir plusieurs éléments de mappage.|  
|`@>`|Fichier hint spécifique *-chaîne de remplacement* qui indique la fin d’un jeu d’éléments de mappage.|  
|`#undef` *-nom de l’indicateur*|La directive de préprocesseur qui supprime une indication existante. Le nom de l’indicateur est fourni par le *-nom de l’indicateur* identificateur.|  
|`//` *commentaire*|Une seule ligne de commentaire.|  
|`/*` *commentaire* `*/`|Un commentaire multiligne.|  
  
## <a name="what-macros-require-a-hint"></a>Ce que les Macros nécessitent une indication ?  
 Certains types de macros peuvent perturber le système d’analyse. Cette section décrit les types de macros qui peuvent entraîner un problème et le type d’indicateur, que vous pouvez créer pour résoudre ce problème.  
  
### <a name="disruptive-macros"></a>Macros perturbatrices  
 Certaines macros provoquent le système d’analyse interprète le code source, mais peuvent être ignorées sans gêner votre navigation. Par exemple, le langage d’Annotation de Code Source ([SAL](../c-runtime-library/sal-annotations.md)) macros résoudre aux attributs C++ qui vous aident à rechercher des bogues de programmation. Si vous souhaitez ignorer les annotations SAL lorsque vous parcourez le code, vous souhaiterez créer un fichier hint qui masque l’annotation.  
  
 Dans le code source suivant, le type de paramètre pour le `FormatWindowClassName()` fonction est `PXSTR`, et le nom du paramètre est `szBuffer`. Toutefois, le système d’analyse confond les `_Pre_notnull_` et `_Post_z_` annotations SAL pour le type de paramètre ou le nom du paramètre.  
  
 **Code source :**  
  
```  
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)  
```  
  
 **Stratégie :** définition de Null  
  
 La stratégie dans cette situation consiste à ignorer les annotations SAL comme s’il n’existent pas. Pour ce faire, spécifiez une indication dont la chaîne de remplacement est null. Par conséquent, le système d’analyse ignore les annotations et le **affichage de classes** navigateur ne les affiche pas. (Visual C++ inclut un fichier hint intégré qui masque les annotations SAL.)  
  
 **Fichier hint :**  
  
```  
#define _Pre_notnull_  
```  
  
### <a name="concealed-cc-language-elements"></a>Éléments du langage C/C++ cachés  
 Une raison classique que le système d’analyse interprète le code source est si une macro masque un C/C++ [/ / / délimiteur](../cpp/punctuators-cpp.md) ou [mot-clé](../cpp/keywords-cpp.md) jeton. Autrement dit, une macro peut contenir la moitié d’une paire de signes de ponctuation, tels que `<>`, `[]`, `{}`, et `()`.  
  
 Dans le code source suivant, le `START_NAMESPACE` macro masque une accolade ouvrante non couplée (`{`).  
  
 **Code source :**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
 **Stratégie :** copie directs  
  
 Si la sémantique d’une macro est essentielle à l’expérience de navigation, créez un indicateur qui est identique à la macro. Le système d’analyse résout la macro à la définition dans le fichier hint.  
  
 Notez que si la macro dans le fichier source contienne d’autres macros, ces macros sont interprétées uniquement si elles sont déjà dans le jeu d’indications effectives.  
  
 **Fichier hint :**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
### <a name="maps"></a>Mappages  
 Un mappage est composé de macros qui désignent un élément de début, élément de fin et zéro ou plusieurs éléments intermédiaires. Le système d’analyse interprète les mappages, car chaque macro de mappage masque des éléments de langage C/C++, et la syntaxe d’une instruction C/C++ complète est répartie sur plusieurs macros différentes.  
  
 Le code source suivant définit les `BEGIN_CATEGORY_MAP`, `IMPLEMENTED_CATEGORY`, et `END_CATEGORY_MAP` macros.  
  
 **Code source :**  
  
```  
#define BEGIN_CATEGORY_MAP(x)\  
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\  
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {  
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },  
#define END_CATEGORY_MAP()\  
   { _ATL_CATMAP_ENTRY_END, NULL } };\  
   return( pMap ); }  
```  
  
 **Stratégie :** identifier les éléments de mappage  
  
 Spécifiez des indications pour le début, intermédiaire (le cas échéant) et de fin, les éléments d’un mappage. Utilisez les chaînes de remplacement de mappage spéciales, `@<`, `@=`, et `@>`. Pour plus d’informations, consultez la `Syntax` dans cette rubrique.  
  
 **Fichier hint :**  
  
```  
// Start of the map.  
#define BEGIN_CATEGORY_MAP(x) @<  
// Intermediate map element.  
#define IMPLEMENTED_CATEGORY( catid ) @=  
// Intermediate map element.  
#define REQUIRED_CATEGORY( catid ) @=  
// End of the map.  
#define END_CATEGORY_MAP() @>  
```  
  
### <a name="composite-macros"></a>Macros composite  
 Macros composite contient au moins un des types de macro confondez pas le système d’analyse.  
  
 Le code source suivant contient la `START_NAMESPACE` (macro), qui spécifie le début d’une portée espace de noms, et le `BEGIN_CATEGORY_MAP` macro, qui spécifie le début d’un mappage.  
  
 **Code source :**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
 **Stratégie :** copie directs  
  
 Créez des indications pour la `START_NAMESPACE` et `BEGIN_CATEGORY_MAP` macros, puis créez une indication pour le `NSandMAP` macro qui est identique à celle indiquée précédemment pour le code source. Ou bien, si une macro composite consiste uniquement des espaces blancs ou des macros sans interruption, vous pouvez définir une indication dont la chaîne de remplacement est une définition de valeur null.  
  
 Dans cet exemple, supposons que `START_NAMESPACE` ait déjà une indication comme décrit dans cette rubrique dans le `Concealed C/C++ Language Elements` sous-titre. Et supposons que `BEGIN_CATEGORY_MAP` ait une indication comme décrit précédemment dans `Maps`.  
  
 **Fichier hint :**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
### <a name="inconvenient-macros"></a>Macros gênantes  
 Certaines macros peuvent être interprétées par le système d’analyse, mais le code source est difficile à lire parce que la macro est longue ou complexe. Pour améliorer la lisibilité, vous pouvez fournir une indication qui simplifie l’affichage de la macro.  
  
 **Code source :**  
  
```  
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)  
```  
  
 **Stratégie :** Simplification  
  
 Créer un indicateur qui affiche une définition de macro plus simple.  
  
 **Fichier hint :**  
  
```  
#define STDMETHOD(methodName) void* methodName  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre comment des indications sont accumulées à partir de fichiers hint. Fichiers de mots vides ne sont pas utilisés dans cet exemple.  
  
 L’illustration suivante décrit certains des répertoires physiques dans un projet Visual C++. Fichiers hint se trouvent dans le `vcpackages`, `Debug`, `A1`, et `A2` répertoires.  
  
### <a name="hint-file-directories"></a>Répertoires de fichiers hint  
 ![Communes et projet &#45 ; répertoires de fichiers hint spécifique.](../ide/media/hintfile.png "HintFile")  
  
### <a name="directories-and-hint-file-contents"></a>Répertoires et contenu des fichiers Hint  
 La liste suivante indique les répertoires dans ce projet qui contiennent des fichiers hint, ainsi que le contenu de ces fichiers hint. Seules certaines des différentes indications contenues dans le `vcpackages` fichier hint du répertoire sont répertoriés.  
  
-   vcpackages  
  
    ```  
    // vcpackages (partial list)  
    #define _In_  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    ```  
  
-   Débogage  
  
    ```  
    // Debug  
    #undef _In_  
    #define OBRACE {  
    #define CBRACE }  
    #define RAISE_EXCEPTION(x) throw (x)  
    #define START_NAMESPACE namespace MyProject {  
    #define END_NAMESPACE }  
    ```  
  
-   A1  
  
    ```  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {  
    ```  
  
-   A2  
  
    ```  
    // A2  
    #undef OBRACE  
    #undef CBRACE  
    ```  
  
### <a name="effective-hints"></a>Indications effectives  
 Le tableau suivant répertorie les indications effectives pour les fichiers sources de ce projet.  
  
-   Fichier source : A1_A2_B.cpp  
  
-   Indications effectives :  
  
    ```  
    // vcpackages (partial list)  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    // Debug...  
    #define RAISE_EXCEPTION(x) throw (x)  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {   
    // ...Debug  
    #define END_NAMESPACE }  
    ```  
  
 Les remarques suivantes s’appliquent à la liste précédente.  
  
-   Les indications effectives proviennent du `vcpackages`, `Debug`, `A1`, et `A2` répertoires.  
  
-   Le **#undef** directive dans le `Debug` fichier hint supprimé le `#define _In_` indicateur dans le `vcpackages` fichier hint du répertoire.  
  
-   Le fichier hint dans la `A1` redéfinit le répertoire `START_NAMESPACE`.  
  
-   Le `#undef` indicateur dans le `A2` directory supprimé les indications pour `OBRACE` et `CBRACE` dans les `Debug` fichier hint du répertoire.  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Création et contrôle de l’environnement Windows](../Topic/Creating%20and%20Controlling%20Environment%20Windows.md)   
 [#define, Directive (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)   
 [#undef (directive) (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)   
 [Annotations SAL](../c-runtime-library/sal-annotations.md)   
 [Tables des messages](../mfc/reference/message-maps-mfc.md)   
 [Macros de mappage des messages](../atl/reference/message-map-macros-atl.md)   
 [Macros de mappage d’objet](../atl/reference/object-map-macros.md)