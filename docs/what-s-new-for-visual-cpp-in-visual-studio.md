---
title: "Nouveautés de Visual C++ dans Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 8/2/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: b90891be2ca726bb6cdd28d024cda68494e69af4
ms.openlocfilehash: 9103da7fb4e10553d2558b15a24bc6a894dd1eff
ms.contentlocale: fr-fr
ms.lasthandoff: 08/15/2017

---

# <a name="whats-new-for-visual-c-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Nouveautés de Visual C++ dans [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] comprend un grand nombre de mises à jour et de correctifs de l’environnement Visual C++. Nous avons corrigé plus de 250 bogues et signalé des problèmes dans le compilateur et les outils, dont la plupart avaient été soumis par des clients via [Microsoft Connect](https://connect.microsoft.com/VisualStudio "Microsoft Connect"). Merci d’avoir signalé ces bogues.  Pour plus d’informations sur les nouveautés de l’ensemble de Visual Studio, visitez le site [Nouveautés de [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]](https://go.microsoft.com/fwlink/?linkid=834481).

<!--The compiler and tools version number in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] is 14.10.24629. -->


## <a name="c-compiler"></a>Compilateur C++

### <a name="c-conformance-improvements"></a>Améliorations de la conformité de C++
Dans cette version, nous avons mis à jour le compilateur C++ et la bibliothèque standard avec prise en charge améliorée des fonctionnalités C++11 et C++14, et nous avons ajouté la prise en charge préliminaire de certaines fonctionnalités prévues pour la version C++17 standard. Pour plus d’informations, consultez [Améliorations de la conformité de C++ dans Visual Studio 2017](cpp-conformance-improvements-2017.md).

### <a name="new-compiler-switches"></a>Nouveaux commutateurs du compilateur  

 -**/std:c++14** et **/std:c++latest** : ces commutateurs du compilateur vous permettent de vous abonner à des versions spécifiques du langage de programmation ISO C++ dans un projet. Pour plus d’informations, consultez [-std (Specify Language Standard Version)](build/reference/std-specify-language-standard-version.md). La plupart des nouvelles fonctionnalités standard préliminaires sont protégées par le commutateur /std:c++latest. 

**Visual Studio 2017 version 15.3** : l’option **/std:c++17** active l’ensemble des fonctionnalités C++17 implémentées par le compilateur Visual C++. Cette option désactive la prise en charge du compilateur et de la bibliothèque standard pour les fonctionnalités modifiées ou nouvelles dans les versions plus récentes de Working Draft et les mises à jour de défaut de C++ Standard.

-[/permissive-](build/reference/permissive-standards-conformance.md) : permet d’activer toutes les options de compilateur de conformité aux normes strictes et de désactiver la plupart des extensions du compilateur spécifiques à Microsoft (mais pas __declspec (dllimport), par exemple). (Option désactivée par défaut, mais qui sera activée par défaut à un moment donné dans le futur.)

-[/diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md) : permet l’affichage du numéro de ligne, du numéro de ligne et de la colonne, ou du numéro de ligne et de la colonne avec un signe insertion sous la ligne de code où l’erreur ou l’avertissement de diagnostic a été trouvé.

-[/debug:fastlink](build/reference/debug-generate-debug-info.md) :  
permet une édition de liens incrémentielle jusqu’à 30 % plus rapide (par rapport à Visual Studio 2015) en ne copiant pas toutes les informations de débogage dans le fichier PDB. À la place, le fichier PDB pointe vers les informations de débogage pour les fichiers objets et bibliothèques utilisés pour créer l’exécutable. Consultez [Faster C++ build cycle in VS “15” with /Debug:fastlink](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/) et [Recommendations to speed C++ builds in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/).

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] permet l’utilisation de /sdl avec /await. Nous avons supprimé la limitation de /RTC avec les coroutines. 

### <a name="codegen-security-diagnostics-and-versioning"></a>Codegen, sécurité, diagnostics et gestion de version
Cette version apporte plusieurs améliorations à l’optimisation, à la génération de code, à la gestion de version de l’ensemble d’outils et aux diagnostics. Les améliorations notables sont les suivantes :  

- Amélioration de la génération du code des boucles : prise en charge de la vectorisation automatique de la division d’entiers constants, optimisation de l’identification des modèles de memset.
- Amélioration de la sécurité du code : amélioration de la production du diagnostic de dépassement de mémoire tampon du compilateur ; /guard:cf protège désormais les instructions switch qui génèrent des tableaux de saut.
- Gestion de version : la valeur de la macro de préprocesseur intégrée _MSC_VER est désormais mise à jour de façon monolithique à chaque mise à jour de l’ensemble d’outils Visual C++. Pour plus d’informations, consultez [Visual C++ Compiler Version](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/).
- Nouvelle disposition de l’ensemble d’outils : le compilateur et les outils de génération connexes ont un nouvel emplacement et une structure de répertoire sur votre ordinateur de développement. La nouvelle disposition permet des installations côte à côte de plusieurs versions du compilateur. Pour plus d’informations, consultez [Compiler Tools Layout in Visual Studio "15"](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/).
- Amélioration des diagnostics : la fenêtre Sortie affiche maintenant la colonne où une erreur se produit. Pour plus d’informations, consultez [C++ compiler diagnostics improvements in VS "15" Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Lors de l’utilisation de coroutines, le mot clé expérimental « yield » (disponible sous le commutateur /await) a été supprimé. Votre code doit être mis à jour pour utiliser `co_yield` à la place. Pour plus d’informations, consultez le [blog de l’équipe Visual C++](https://blogs.msdn.microsoft.com/vcblog/). 

**Visual Studio 2017 version 15.3** : améliorations supplémentaires apportées aux diagnostics dans le compilateur. Pour plus d'informations, consultez [Diagnostic Improvements in Visual Studio 2017 15.3.0](https://blogs.msdn.microsoft.com/vcblog/2017/07/21/diagnostic-improvements-in-vs2017-15-3-0/).

## <a name="c-libraries"></a>Bibliothèques C++

### <a name="standard-library-improvements"></a>Améliorations apportées à la bibliothèque standard :

* Améliorations mineures des diagnostics de basic_string _ITERATOR_DEBUG_LEVEL != 0. Le déplacement d’une vérification IDL dans le système des chaînes signale désormais le comportement spécifique qui a provoqué le déplacement. Par exemple, au lieu de « itérateur de chaîne non déréférençable » vous recevez « impossible de déréférencer l’itérateur de chaîne car il est hors limites (par exemple un itérateur de fin) ».
* Amélioration des performances : les surcharges de basic_string::find(char) appellent une seule fois traits::find. Auparavant, ceci était implémenté comme une recherche de chaîne générale d’une chaîne de longueur 1.
* Amélioration des performances : basic_string::operator == vérifie désormais la taille de la chaîne avant de comparer le contenu des chaînes.
* Amélioration des performances : suppression du couplage des contrôles de basic_string, qui rendait difficile l’analyse par l’optimiseur du compilateur. Résout VSO# 262848 « \<string\> : reserve() fait trop de travail ». Notez que pour toutes les chaînes courtes, l’appel de reserve a toujours un coût non nul pour ne rien faire.
* Nous avons ajouté \<any\>, \<string_view\>, apply(), make_from_tuple().
* std::vector a été remanié pour un fonctionnement plus correct et de meilleures performances : les alias utilisés pour l’insertion/emplacement sont désormais gérés correctement conformément à la norme, la garantie d’exception forte est désormais fournie conformément à la norme via move_if_noexcept() et d’autres logiques, et insertion/emplacement réalise moins d’opérations sur les éléments.
* La bibliothèque C++ standard évite désormais de déréférencer les pointeurs fantômes Null.
* Ajout de \<optional\>, \<variant\>, shared_ptr::weak_type et \<cstdalign\>.
* Activation du constexpr C++14 dans min/max/minmax(initializer_list) et min_element/max_element/minmax_element().
* Amélioration des performances de weak_ptr::lock().
* Correction de l’opérateur d’assignation de déplacement std::promise, auparavant susceptible de provoquer le blocage définitif du code.
* Correction des erreurs du compilateur avec la conversion implicite du \<T \*\> atomique en T \*.
* pointer_traits\<Ptr\> détecte désormais correctement Ptr::rebind\<U\>.
* Correction d’un qualificateur const manquant dans l’opérateur de soustraction de move_iterator.
* Correction d’une génération de code silencieuse incorrecte pour les allocateurs avec état définis par l’utilisateur exigeant propagate_on_container_copy_assignment et propagate_on_container_move_assignment.
* Le \<T\> atomique tolère maintenant la fonction operator& () surchargée.
* Pour augmenter le débit du compilateur, les en-têtes de la bibliothèque C++ standard évitent désormais d’inclure des déclarations de fonctions intrinsèques de compilateur inutiles.
* Légère amélioration des diagnostics du compilateur pour les appels bind() incorrects.
* Amélioration de plus de 3 fois des performances des constructeurs de déplacement std::string/std::wstring
* Pour obtenir une liste complète des améliorations de la bibliothèque standard, consultez [Standard Library Fixes In VS 2017 RTM](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/).

#### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 version 15.3

##### <a name="c17-features"></a>Fonctionnalités C++17 
Plusieurs autres fonctionnalités C++17 ont été implémentées. Pour plus d'informations, consultez [Visual C++ Language Conformance](visual-cpp-language-conformance.md).

##### <a name="other-new-features"></a>Autres nouvelles fonctionnalités
* Implémentation de P0602R0 « variant and optional should propagate copy/move triviality ».
* La bibliothèque standard tolère désormais officiellement la désactivation de RTTI dynamique via /GR-. dynamic_pointer_cast() et rethrow_if_nested() requièrent dynamic_cast de manière inhérente, donc la bibliothèque standard les marque en tant que =delete sous /GR-.
* Même lorsque RTTI dynamique a été désactivé via /GR-, « RTTI statique » (sous la forme de typeid(SomeType)) est toujours disponible et alimente plusieurs composants de la bibliothèque standard. La bibliothèque standard prend désormais en charge la désactivation de ce paramètre également, via /D_HAS_STATIC_RTTI=0. *Notez que cette opération désactive std::any, target()et target_type() de std::function, et get_deleter() de shared_ptr.*

##### <a name="correctness-fixes"></a>Correctifs
* Les conteneurs de la bibliothèque standard verrouillent désormais leur max_size() sur numeric_limits\<difference_type\>::max() plutôt que sur max de size_type. Cela garantit que le résultat de distance() sur les itérateurs de ce conteneur est représentable dans le type de retour de distance().
* Spécialisation manquante corrigée auto_ptr\<void\>.
* Les algorithmes meow_n() échouaient précédemment lors de la compilation si l’argument de longueur n’était pas un type intégral ; ils tentent désormais de convertir les longueurs non intégrales sur la valeur difference_type des itérateurs.
* normal_distribution\<float\> n’émet plus d’avertissements dans la bibliothèque standard sur les conversions restrictives de double vers float.
* Correction de certaines opérations basic_string qui effectuaient la comparaison avec npos au lieu de max_size() lors de la vérification du dépassement de taille maximale.
* condition_variable::wait_for(lock, relative_time, predicate) attendait pendant toute la durée du temps relatif en cas de faux éveil. Maintenant, il n’attend que pendant un seul intervalle du temps relatif.
* future::get() invalide désormais le futur, comme l’exige la norme.
* iterator_traits\<void \*\> constituait une erreur matérielle, car il tentait de former void&; il devient désormais une structure vide sans erreur pour autoriser l’utilisation d’iterator_traits dans les conditions SFINAE « is iterator ».
* Certains avertissements signalés par Clang -Wsystem-headers ont été résolus.
* Correction également du problème « la spécification d’exception dans la déclaration ne correspond pas à la déclaration précédente » signalé par Clang -Wmicrosoft-exception-spec.
* Correction également des avertissements d’ordre mem-initializer-list signalés par Clang et C1XX.
* Les conteneurs non ordonnés ne permutaient pas leur hashers ou prédicats lorsque les conteneurs eux-mêmes étaient permutés. C’est le cas désormais.
* Plusieurs opérations de permutation de conteneur sont désormais marquées noexcept (car notre bibliothèque standard ne veut jamais lever une exception lors de la détection de la condition de comportement non définie non-propagate_on_container_swap non-equal-allocator).
* Plusieurs opérations vector\<bool\> sont désormais marquées noexcept.
* La bibliothèque standard applique désormais des value_types d’allocateur correspondantes (en mode C++17) avec une hachure d’échappement d’annulation.
* Correction de certaines conditions où self-range-insert dans basic_strings brouillait le contenu des chaînes. (Remarque : self-range-insert dans vectors est toujours interdit par la norme.)
* basic_string::shrink_to_fit() n’est plus affecté par l’opération propagate_on_container_swap de l’allocateur.
* std::decay gère désormais des types de fonctions abominable (ex. types de fonctions qualifiés cv et/ou qualifiés ref).
* Modification des directives include pour utiliser la casse appropriée et des barres obliques, et améliorer la portabilité.
* Correction de l’avertissement C4061 « l’énumérateur 'Meow' dans le switch de l’énum 'Kitten' n’est pas géré explicitement par une étiquette case ». Cet avertissement est désactivé par défaut et a été résolu en tant qu’exception à la stratégie générale de la bibliothèque standard pour les avertissements. (La bibliothèque standard est sans erreur /W4, mais n’essaie pas d’être sans erreur /Wall. Plusieurs avertissements désactivés par défaut sont très bruyants et ne sont pas destinés à être utilisés de manière régulière.)
* Amélioration des vérifications de débogage de std::list. Les itérateurs de liste vérifient désormais operator->() et liste::unique() marque maintenant les itérateurs comme non valides.
* Correction de la métaprogrammation uses-allocator dans le tuple.

##### <a name="performancethroughput-fixes"></a>Correctifs de performances / de débit
* Contournement des interactions avec noexcept qui empêchaient l’incorporation de l’implémentation std::atomic dans des fonctions qui utilisent la gestion des exceptions structurées (SEH).
* Modification de la fonction _Deallocate() interne de la bibliothèque standard pour l’optimiser dans du code plus petit, ce qui lui permet d’être incorporée dans plus d’emplacements.
* Modification de std::try_lock() pour utiliser l’expansion de package au lieu de la récurrence.
* Amélioration de l’algorithme de prévention de blocage std::lock() pour utiliser des opérations lock() au lieu d’effectuer une rotation sur try_lock() de tous les verrous.
* Activation de l’optimisation de la valeur de retour nommée dans system_category::message().
* La jonction et la disjonction instancient maintenant des types N + 1, au lieu de types 2N + 2.
* std::function n’instancie plus les machines de prise en charge d’allocateur pour chaque type-erased pouvant être appelé, améliorant le débit et réduisant la taille .obj dans les programmes qui transmettent de nombreux lambdas distincts à std::function.
* allocator_traits\<std::allocator\> contient des opérations std::allocator intégrées manuellement, ce qui réduit la taille du code dans le code qui interagit avec std::allocator via allocator_traits (ex. la plupart du code).
* L’interface d’allocateur minimale C++11 est désormais gérée directement par l’allocateur appelant de la bibliothèque standard allocator_traits, au lieu d’inclure l’allocateur dans une classe interne _Wrap_alloc. Cela réduit la taille du code généré pour la prise en charge de l’allocateur, améliore la capacité de l’optimiseur à raisonner à propos des conteneurs de la bibliothèque standard dans certains cas et fournit une meilleure expérience de débogage (car vous voyez désormais votre type d’allocateur, plutôt que _Wrap_alloc\<votre type d’allocateur\> dans le débogueur).
* Suppression de la métaprogrammation pour allocator::reference personnalisé, que les allocateurs ne sont pas autorisés à personnaliser. (Les allocateurs peuvent demander aux conteneurs d’utiliser des pointeurs fantaisistes mais pas des références fantaisistes.)
* Le serveur frontal du compilateur a appris à désencapsuler les itérateurs de débogage dans des opérations for-loops basées sur plage, pour améliorer les performances des versions de débogage.
* Le chemin shrink interne de basic_string pour shrink_to_fit() et reserve() n’est plus dans le chemin des opérations de réaffectation, réduisant la taille du code pour tous les membres en mutation.
* Le chemin grow interne de basic_string n’est plus dans le chemin de shrink_to_fit().
* Les opérations de mutation de basic_string sont désormais incluses dans les fonctions de non allocation de chemin d’accès rapide et d’allocation de chemin d’accès lent, rendant plus susceptible l’intégration du cas no-reallocate fréquent dans les appelants.
* Les opérations de mutation de basic_string construisent désormais des mémoires tampons réaffectées dans l’état désiré plutôt que de les redimensionner en place. Par exemple, l’insertion au début d’une chaîne déplace maintenant le contenu après l’insertion une seule fois (vers le bas ou vers la mémoire tampon qui vient d’être allouée), au lieu de deux fois dans le cas de la réaffectation (vers la mémoire tampon qui vient d’être allouée, puis vers le bas).
* Les opérations appelant la bibliothèque standard C dans \<string\> mettent maintenant en cache l’adresse errno pour supprimer l’interaction répétées avec TLS.
* Implémentation is_pointer simplifiée.
* Fin de la modification de Expression SFINAE basée sur fonction vers une valeur basée sur struct/void_t.
* Désormais, les algorithmes de la bibliothèque standard évitent la post-incrémentation des itérateurs.
* Correction des avertissements de troncation lors de l’utilisation d’allocateurs 32 bits sur les systèmes 64 bits.
* L’assignation de déplacement std::vector est désormais plus efficace dans le cas non-POCMA non-equal-allocator, en réutilisant le tampon lorsque cela est possible.

##### <a name="readability-and-other-improvements"></a>Lisibilité et autres améliorations
* La bibliothèque standard utilise désormais C++14 constexpr sans condition, au lieu de macros définies de façon conditionnelle.
* La bibliothèque standard utilise désormais les modèles d’alias en interne.
* La bibliothèque standard utilise désormais nullptr en interne, au lieu de nullptr_t{}. (L’utilisation interne de NULL a été supprimée. L’utilisation interne de 0-as-null est en cours de nettoyage progressif.)
* La bibliothèque standard utilise désormais std::move() en interne, au lieu d’une mauvaise utilisation stylistique de std::forward().
* Modification de static_assert(false, « message ») en #error message. Cela permet d’améliorer les diagnostics du compilateur car #error arrête immédiatement la compilation.
* La bibliothèque standard ne marque plus les fonctions en tant que __declspec(dllimport). La technologie de l’éditeur de liens moderne ne requiert plus cela.
* Extraction de SFINAE dans des arguments de modèle par défaut, ce qui réduit l’encombrement par rapport aux types de retour et aux types d’arguments de fonction.
* Les vérifications de débogage dans \<random\> utilisent désormais les machines habituelles de la bibliothèque standard, au lieu de la fonction interne _Rng_abort() qui appelait fputs() dans stderr. L’implémentation de cette fonction est conservée pour la compatibilité binaire, mais a été supprimée dans la prochaine version non compatible binaire de la bibliothèque standard. 

### <a name="open-source-library-support"></a>Prise en charge de la bibliothèque open source  
Vcpkg est un outil en ligne de commande open source qui simplifie grandement le processus d’acquisition et de création des bibliothèques statiques C++ open source et DLL dans Visual Studio. Pour plus d’informations, consultez [vcpkg : Gestionnaire de package pour C++](vcpkg.md).

### <a name="cpprest-sdk-290"></a>SDK C++ REST 2.9.0  
Le SDK C++ REST, une API web multiplateforme pour C++, a été mis à jour vers la version 2.9.0. Pour plus d’informations, consultez [CppRestSDK 2.9.0 is available on GitHub](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL
* Un autre ensemble de corrections de la conformité de la recherche de noms
* Les constructeurs de déplacement et les opérateurs d’assignation de déplacement existants sont désormais correctement marqués comme ne levant pas d’exceptions
* Annulation de la suppression de l’avertissement valide C4640 sur l’initialisation sécurisée de thread des statiques locales dans atlstr.h
* L’initialisation sécurisée de thread des statiques locales était automatiquement désactivée dans l’ensemble d’outils XP avec [utilisation d’ATL ET construction d’une DLL]. Cela n'est plus le cas. Vous pouvez ajouter /Zc:threadSafeInit dans les paramètres de votre projet si vous voulez que l’initialisation sécurisée de thread soit désactivée. 

### <a name="visual-c-runtime"></a>Runtime Visual C++
* Nouvel en-tête « cfguard.h » pour les symboles de protection de flux de contrôle. 

## <a name="c-ide"></a>IDE C++

* Les performances des modifications de configuration sont désormais meilleures pour les projets natifs C++ et bien meilleures pour les projets C++/CLI. Quand une configuration de solution est activée pour la première fois, elle est désormais plus rapide et toutes les activations suivantes de cette configuration de solution sont presque instantanées.

**Visual Studio 2017 version 15.3** :
* Plusieurs Assistants de projet et de code ont été réécrits pour refléter le style particulier des boîtes de dialogue.
* **Ajouter une classe** lance désormais l’Assistant Ajouter une classe directement. Tous les autres éléments qui se trouvaient déjà ici sont maintenant disponibles sous **Ajouter > Nouvel élément**.
* Les projets Win32 se trouvent désormais sous la catégorie Windows Desktop dans la boîte de dialogue **Nouveau projet**.
* Les modèles Console Windows et Application de bureau créent à présent les projets sans afficher d’Assistant. Un nouvel Assistant Windows Desktop se trouve sous la même catégorie qui affiche toujours les mêmes options.

### <a name="intellisense"></a>IntelliSense  
* Le nouveau moteur de base de données SQLite est désormais celui utilisé par défaut. Ceci permet d’accélérer les opérations de base de données, comme que « Atteindre la définition » ou « Rechercher toutes les références », et d’améliorer considérablement le temps d’analyse de la solution initiale. Le paramètre a été déplacé dans Outils > Options > Éditeur de texte > C/C++ > Avancé (il se trouvait auparavant sous (...) C/C++ > Expérimental).

* Nous avons amélioré les performances d’IntelliSense dans les projets et fichiers qui n’utilisent pas d’en-têtes précompilés : un en-tête précompilé automatique est créé pour les en-têtes du fichier en cours.

* Nous avons ajouté une fonctionnalité de filtrage des erreurs et une aide pour les erreurs IntelliSense figurant dans la liste d’erreurs. Le fait de cliquer sur la colonne d’erreur permet maintenant un filtrage. De plus, en cliquant sur une erreur spécifique ou sur F1, une recherche en ligne est lancée sur le message d’erreur concerné.

  ![Liste d’erreurs](media/ErrorList1.png "Liste d’erreurs")

  ![Liste d’erreurs filtrée](media/ErrorList2.png "Liste d’erreurs filtrée")

* Ajout de la possibilité de filtrer les éléments de la liste des membres par type.

  ![Filtrage de la liste des membres](media/mlfiltering.png "Filtrage de la liste des membres")

* Ajout d’une nouvelle fonctionnalité IntelliSense prédictive expérimentale qui fournit un filtrage en fonction du contexte de ce qui apparaît dans la liste des membres. Consultez [C++ IntelliSense Improvements - Predictive IntelliSense & Filtering](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)

* L’option Rechercher toutes les références (Maj+F12) vous aide maintenant à naviguer facilement, même dans des codes base complexes. Elle offre des options avancées de regroupement, de filtrage, de tri, de recherche dans les résultats et (pour certains langages) la colorisation, ce qui vous permet d’avoir une vision claire de vos références. Pour C++, la nouvelle interface utilisateur inclut des informations indiquant si nous lisons ou si nous écrivons dans une variable.

* La fonctionnalité IntelliSense Point par flèche a été changée de « expérimentale » en « avancée » et elle est maintenant activée par défaut. Les fonctionnalités de l’éditeur Développer les étendues et Développer la priorité ont également été changées de « expérimentales » en « avancées ».

* Les fonctionnalités de refactorisation expérimentales Modifier la signature et Extraire la fonction sont désormais disponibles par défaut.

* La fonctionnalité expérimentale pour le « Chargement accéléré des projets » pour les projets C++. La prochaine fois que vous ouvrirez un projet C++, celui-ci sera chargé plus rapidement, et la fois suivante encore plus rapidement.

Certaines de ces fonctionnalités sont communes à d’autres langages, et certaines sont spécifiques à C++. Pour plus d’informations sur ces nouvelles fonctionnalités, consultez [Announcing Visual Studio “15”](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/). 


### <a name="support-for-non-msbuild-projects-with-open-folder"></a>Prise en charge de projets non-MSBuild avec Ouvrir le dossier
Visual Studio 2017 introduit la fonctionnalité « Ouvrir le dossier », qui vous permet d’effectuer des opérations de codage, de génération et de débogage dans un dossier contenant le code source sans avoir à créer des solutions ni des projets. Il est ainsi beaucoup plus simple de bien démarrer avec Visual Studio, même si votre projet n’est pas un projet MSBuild. Avec « Ouvrir le dossier », vous pouvez accéder aux puissantes fonctionnalités de compréhension du code, de modification, de génération et de débogage que Visual Studio fournit déjà pour les projets MSBuild. Pour plus d’informations, consultez [Open Folder projects in Visual C++](ide/non-msbuild-projects.md).

* Améliorations de l’expérience de la fonctionnalité Ouvrir le dossier. Vous pouvez personnaliser l’expérience via ces fichiers .json :
  - CppProperties.json pour personnaliser l’expérience IntelliSense et l’expérience de navigation.
  - Tasks.json pour personnaliser les étapes de la génération. 
  - Launch.json pour personnaliser l’expérience du débogage.

**Visual Studio 2017 version 15.3** : 
* Amélioration de la prise en charge d’autres compilateurs et environnements de génération tels que MinGW et Cygwin. Pour plus d’informations, consultez [Using MinGW and Cygwin with Visual C++ and Open Folder](https://blogs.msdn.microsoft.com/vcblog/2017/07/19/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/).
* Ajout de la prise en charge de la définition de variables d’environnement globales et propres à la configuration dans CppProperties.json et CMakeSettings.json. Ces variables d’environnement peuvent être consommées par des configurations de débogage définies dans launch.vs.json et des tâches dans tasks.vs.json.
* Amélioration de la prise en charge du générateur Ninja de CMake, y compris la possibilité de facilement cibler des plateformes 64 bits.

### <a name="cmake-support-via-open-folder"></a>Prise en charge de CMake via Ouvrir le dossier
Visual Studio 2017 introduit la prise en charge de l’utilisation de projets CMake sans les convertir en fichiers projet MSBuild (.vcxproj). Pour plus d’informations, consultez [CMake projects in Visual C++](ide/cmake-tools-for-visual-cpp.md). L’ouverture de projets CMake avec « Ouvrir le dossier » configure automatiquement l’environnement pour la modification, la génération et le débogage en C++.

* IntelliSense pour C++ fonctionne sans qu’il soit nécessaire de créer un fichier CppProperties.json dans le dossier racine. En outre, nous avons ajouté une nouvelle liste déroulante pour permettre aux utilisateurs de basculer facilement entre les configurations fournies par les fichiers CMake et CppProperties.json.

* Des options de configuration supplémentaires sont prises en charge via un fichier CMakeSettings.json qui se trouve dans le même dossier que le fichier CMakeLists.txt.

  ![CMake – Ouvrir le dossier](media/cmake_cpp.png "CMake – Ouvrir le dossier")

**Visual Studio 2017 version 15.3** : ajout de la prise en charge du générateur Ninja de CMake. Pour plus d’informations, consultez [CMake support in Visual Studio – what’s new in 2017 15.3 Preview 2](https://blogs.msdn.microsoft.com/vcblog/2017/06/14/cmake-support-in-visual-studio-whats-new-in-2017-15-3-preview-2/). 

## <a name="c-installation-workloads"></a>Charges de travail d’installation C++ 

### <a name="windows-desktop-development-with-c"></a>Développement Windows Desktop avec C++ :  
Nous fournissons à présent une expérience d’installation plus fine pour la charge de travail C++ d’origine. Nous avons ajouté des composants sélectionnables qui vous permettent d’installer uniquement les outils dont vous avez besoin.  Notez que les tailles d’installation indiquées pour les composants répertoriés dans l’interface utilisateur du programme d’installation ne sont pas exactes et sous-estiment la taille totale.

Pour créer correctement des projets Win32 dans la charge de travail de bureau C++, vous devez installer un ensemble d’outils et un SDK Windows. L’installation des composants recommandés (sélectionnés) « Ensemble d’outils VC++ 2017 v141 (x86,x64) » et « SDK Windows 10 (10.0.14393) » assure un bon fonctionnement. Si les outils nécessaires ne sont pas installés, les projets ne sont pas correctement créés et l’Assistant se bloque.

### <a name="linux-development-with-c"></a>Développement Linux avec C++ :  
L’extension populaire [Visual C++ pour le développement Linux](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) fait désormais partie de Visual Studio. Cette installation fournit tout ce dont vous avez besoin pour développer et déboguer des applications C++ exécutées dans un environnement Linux.  

**Visual Studio 2017 version 15.2** : améliorations pour le partage de code inter-plateformes et la visualisation de type. Pour plus d’informations, consultez [Linux C++ improvements for cross-platform code sharing and type visualization](https://blogs.msdn.microsoft.com/vcblog/2017/05/10/linux-cross-platform-and-type-visualization/).

### <a name="game-development-with-c"></a>Développement de jeux avec C++ :  
Utilisez toute la puissance de C++ pour créer des jeux professionnels reposant sur DirectX ou Cocos2d.  

### <a name="mobile-development-with-c-android-and-ios"></a>Développement d’applications mobiles avec C++ (Android et iOS) :  
Vous pouvez désormais créer et déboguer des applications mobiles, à l’aide de Visual Studio, capables de cibler Android et iOS.  

### <a name="universal-windows-apps"></a>Applications universelles Windows :  
C++ est fourni sous forme de composant facultatif pour la charge de travail Application Windows universelle.  Actuellement, la mise à niveau des projets C++ doit être effectuée manuellement. Si vous ouvrez un projet UWP ciblé pour v140 dans Visual Studio 2017, vous devez sélectionner l’ensemble d’outils de plateforme v141 dans les pages des propriétés du projet si Visual Studio 2015 n’est pas installé.

## <a name="new-options-for-c-on-universal-windows-platform"></a>Nouvelles options pour C++ sur la plateforme universelle Windows
Vous avez maintenant de nouvelles options pour l’écriture et l’empaquetage des applications C++ pour la plateforme universelle Windows et le Windows Store : vous pouvez utiliser Desktop App Converter pour empaqueter votre application de bureau existante pour le déploiement via le Windows Store. Pour plus d’informations, consultez [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project/) et [Déplacer votre application de bureau vers la plateforme universelle Windows (UWP) avec le pont du bureau](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

Lors de l’écriture de nouveau code, vous pouvez désormais utiliser C++/WinRT, une projection de langage C++ standard pour Windows Runtime (WinRT) implémentée uniquement dans les fichiers d’en-tête. Il vous permet à la fois de créer et de consommer des API Windows Runtime à l’aide d’un compilateur C++ conforme aux normes. C++/WinRT est conçu pour offrir aux développeurs C++ un accès idéal à l’API Windows moderne. Pour plus d’informations, consultez [C++/WinRT disponible sur GitHub](https://moderncpp.com/).


## <a name="clangc2-platform-toolset"></a>Outils de plateforme Clang/C2
L’ensemble d’outils Clang/C2 qui est fourni avec [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] prend désormais en charge le commutateur /bigobj, qui est essentiel pour la création de gros projets. Il inclut également plusieurs résolutions de bogues importantes, à la fois au niveau du front-end et du back-end du compilateur.

## <a name="c-code-analysis"></a>Analyse du code C++

Les vérificateurs principaux C++ permettant d’appliquer les [directives principales C++](https://github.com/isocpp/CppCoreGuidelines) sont désormais distribués avec Visual Studio. Il suffit d’activer les vérificateurs dans la boîte de dialogue Code Analysis Extensions (Extensions d’analyse du code) des pages de propriétés du projet pour que les extensions soient incluses lorsque vous exécutez l’analyse du code. 

![CppCoreCheck](media/CppCoreCheck.png "Page de propriétés CppCoreCheck") 

**Visual Studio 2017 version 15.3** : ajout de la prise en charge des règles liées à la gestion de ressources. Pour plus d’informations, consultez [Using the C++ Core Guidelines checkers](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

## <a name="unit-testing"></a>Test unitaire

Les nouvelles extensions Visual Studio vous permettent d’exécuter vos tests unitaires en fonction de Google Test et de Boost.Test directement dans Visual Studio. Pour plus d’informations, consultez [C++ Unit Testing Updates: Announcing Boost.Test Adapter and Improved Google Test Support](https://blogs.msdn.microsoft.com/vcblog/2017/08/04/c-unit-testing-updates-announcing-boost-test-adapter-and-improved-google-test-support/).

## <a name="visual-studio-graphics-diagnostics"></a>Diagnostics des graphiques Visual Studio

Visual Studio Graphics Diagnostics est un ensemble d’outils pour l’enregistrement, puis l’analyse des problèmes de rendu et de performances des applications Direct3D. Les fonctionnalités Graphics Diagnostics peuvent être utilisées sur les applications qui s’exécutent localement sur votre PC Windows, dans un émulateur d’appareil Windows, ou sur un PC ou un appareil distant.

* **Entrées et sorties pour les nuanceurs de sommets et de géométrie :** la possibilité d’afficher les entrées et sorties des nuanceurs de sommets et de géométrie a été l’une des fonctionnalités les plus demandées et est maintenant prise en charge dans les outils. Il vous suffit de sélectionner l’étape VS ou GS dans la vue Étapes de canalisation pour commencer à examiner ses entrées et sorties dans le tableau ci-dessous.

  ![Entrées/sorties pour les nuanceurs](media/io-shaders.png)

* **Recherche et filtrage dans la table des objets :** fournit un moyen rapide et facile de trouver les ressources que vous recherchez.

  ![Rechercher](media/search.png)
   
* **Historique des ressources :** cette nouvelle vue offre une façon simplifiée d’afficher tout l’historique des modifications d’une ressource utilisée pendant le rendu d’un frame capturé. Pour appeler l’historique d’une ressource, cliquez simplement sur l’icône de l’horloge en regard d’un lien hypertexte de ressource.

  ![Historique des ressources](media/resource-history.png)

  La nouvelle fenêtre Outil Historique des ressources s’affiche, remplie avec l’historique des modifications de la ressource.

  ![Modification de l’historique des ressources](media/resource-history-change.png)

  Notez que si votre frame a été capturé avec la capture de pile des appels complète activée (**Visual Studio > Outils > Options > Graphics Diagnostics**), le contexte de chaque événement de modification peut être rapidement déduit et inspecté dans votre projet Visual Studio.  

* **Statistiques d’API :** affichez une synthèse générale de l’utilisation des API dans votre frame. Cela peut être pratique pour détecter des appels dont vous ne vous rendez pas compte ou des appels trop nombreux. Cette fenêtre est disponible via **View (Afficher) > Statistiques d’API** dans Visual Studio Graphics Analyzer.

  ![Statistiques d’API](media/api-stats.png)

* **Statistiques de la mémoire :** affichez la quantité de mémoire que le pilote alloue pour les ressources que vous créez dans le frame. Cette fenêtre est disponible via View (Afficher) > Statistiques de la mémoire dans Visual Studio Graphics Analyzer. Les données peuvent être copiées dans un fichier CSV pour être affichées dans une feuille de calcul en cliquant avec le bouton droit et en choisissant Copier tout.

  ![Statistiques de la mémoire](media/memory-stats.png)
 
* **Validation du frame :** la nouvelle liste d’erreurs et d’avertissements facilite la navigation dans votre liste d’événements basée sur les éventuels problèmes détectés par la couche de débogage Direct3D. Cliquez sur View (Afficher)-> Validation du frame dans Visual Studio Graphics Analyzer pour ouvrir la fenêtre. Cliquez ensuite sur Exécuter la validation pour commencer l’analyse. L’opération peut prendre plusieurs minutes, selon la complexité du frame.

  ![Validation du frame](media/frame-validation.png)
 
* **Analyse des frames pour D3D12 :** utilisez l’analyse des frames pour analyser les performances des appels de dessin avec des expériences de simulations dirigées. Basculez vers l’onglet Analyse des frames et lancez l’analyse pour afficher le rapport. Pour plus d’informations, regardez la vidéo [GoingNative 25: Visual Studio Graphics Frame Analysis](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool).

  ![Analyse des frames](media/frame-analysis.png)

* **Améliorations de l’utilisation du GPU :** ouvrez les suivis effectués via le profileur de l’utilisation du GPU Visual Studio avec le mode GPU ou l’outil Windows Performance Analyzer (WPA) pour une analyse plus détaillée. Si Windows Performance Toolkit est installé, deux liens hypertexte s’affichent, un pour WPA et l’autre pour le mode GPU, en bas à droite de la vue d’ensemble de la session.

  ![Utilisation du GPU](media/gpu-usage.png)
 
  Les suivis ouverts en mode GPU via ce lien prennent en charge le zoom et le panoramique synchronisés dans la chronologie entre Visual Studio et le mode GPU. Une case à cocher dans Visual Studio permet de contrôler si la synchronisation est activée ou non. 

  ![Mode GPU](media/gpu-view.png) 


 

