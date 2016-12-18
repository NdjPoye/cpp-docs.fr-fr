---
title: "Nouveaut&#233;s de Visual&#160;C++ dans Visual Studio&#160;2015 | Microsoft Docs"
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
ms.assetid: 1cc09fad-85a2-43c2-b022-bb99f5fe0ad7
caps.latest.revision: 101
caps.handback.revision: 101
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Nouveaut&#233;s de Visual&#160;C++ dans Visual Studio&#160;2015
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans Visual Studio 2015, le compilateur C\+\+ et la bibliothèque standard bénéficient d'une prise en charge améliorée pour C\+\+11 et d'une prise en charge initiale pour certaines fonctionnalités C\+\+14.  Ils comprennent également une prise en charge préliminaire pour certaines fonctionnalités prévues dans la version C\+\+17 standard.  
  
 Nous avons également ajouté des modèles de projet pour le développement multiplateforme sur plusieurs appareils sur [Android et iOS](../Topic/Visual%20C++%20for%20Cross-Platform%20Mobile%20Development.md), apporté des améliorations aux fonctionnalités de [diagnostic](#BK_Diagnostics) et de [productivité](#BK_IDE), et amélioré de manière significative le [temps de génération](#BK_FasterBuildTimes).  
  
> [!WARNING]
>  Dans Visual Studio 2015, Visual C\+\+ n'est pas installé par défaut.  Lors de l'installation, veillez à choisir l'installation **Personnalisée**, puis les composants C\+\+ dont vous avez besoin.  Ou, si Visual Studio est déjà installé, choisissez **Fichier &#124; Nouveau &#124; Projet &#124; C\+\+** et vous serez invité à installer les composants nécessaires.  
  
 Pour plus d'informations sur les autres ajouts effectués dans Visual Studio 2015, consultez [Nouveautés de Visual Studio 2015](../Topic/What's%20New%20in%20Visual%20Studio%202015.md).  
  
 Dans cette rubrique :  
  
1.  [Compilateur](#BK_Compiler)  
  
2.  [Bibliothèque standard C++](#BK_CppStdLib)  
  
3.  [Bibliothèque Runtime C](#BK_CRT)  
  
4.  [Temps de génération améliorés](#BK_FasterBuildTimes)  
  
5.  [Performances et qualité du code](#BK_PerfCodeQuality)  
  
6.  [Productivité, débogage et diagnostics](#BK_IDE)  
  
    1.  [IntelliSense avec un fichier unique](#BK_SingleFileIntelliSense)  
  
    2.  [Refactorisation](#BK_Refactoring)  
  
    3.  [Améliorations de la base de données du programme](#BK_PDB)  
  
    4.  [Diagnostics](#BK_Diagnostics)  
  
7.  [Ciblage de Windows 10](#BK_Win10)  
  
8.  [Graphics Diagnostics](#BK_GraphicsDiagnostics)  
  
9. [Nouvel outil d'utilisation du GPU](#BK_GPUUsage)  
  
10. [Nouvelles fonctionnalités MFC](#BK_MFC)  
  
## Prise en charge des normes ISO C\/C\+\+  
  
###  <a name="BK_Compiler"></a> Compilateur  
  
-   **Fonctions pouvant être reprises \(resume\/await\)** Les mots clés resume et await offrent une prise en charge au niveau du langage pour la programmation asynchrone et permettent l'utilisation de fonctions pouvant être reprises.  Pour le moment, cette fonctionnalité est toujours expérimentale et est uniquement disponible pour les cibles x64.  **\(Proposé pour C\+\+17 \[N3858\]\)**  
  
-   **Expressions lambda génériques \(polymorphiques\)** Les types de paramètres des fonctions lambda peuvent désormais être spécifiés avec la fonction auto. Le compilateur interprète la fonction auto dans ce contexte de la manière suivante : l'opérateur d'appel de la fonction de clôture est un modèle de fonction membre et chaque utilisation de la fonction auto dans une expression lambda correspond à un paramètre de type modèle distinct.  **\(C\+\+14\)**  
  
-   **Expressions de capture lambda généralisées** Également appelées init\-capture.  Le résultat d'une expression arbitraire peut désormais être attribué à une variable dans la clause capture d'une expression lambda.  Les types move\-only peuvent ainsi être capturés par valeur, et l'expression lambda peut définir des membres de données arbitraires dans son objet clôture.  **\(C\+\+14\)**  
  
-   **Littéraux binaires** Les littéraux binaires sont désormais pris en charge.  Ces littéraux commencent par 0B ou 0b et sont composés uniquement des chiffres 0 et 1.  **\(C\+\+14\)**  
  
-   **Déduction de type Return** Le type Return des fonctions normales peut désormais être déduit, y compris pour les fonctions contenant plusieurs instructions Return et les fonctions récursives.  Les définitions de ces fonctions sont précédées du mot clé auto comme pour les définitions de fonction contenant un type Return final, sauf que celui\-ci est omis.  **\(C\+\+14\)**  
  
-   **decltype\(auto\)** La déduction de type à l'aide du mot clé auto pour initialiser les expressions supprime les qualificateurs ref et les qualificateurs cv de niveau supérieur de l'expression.  La fonction decltype\(auto\) conserve ces qualificateurs ref et cv, et peut désormais être utilisée partout où la fonction auto peut être utilisée, sauf pour introduire une fonction avec un type déduit ou Return final.  **\(C\+\+14\)**  
  
-   **Génération implicite de fonctions Déplacer un membre spécial** Les constructeurs de déplacement et les opérateurs d'assignation de déplacement sont désormais générés de manière implicite lorsque les conditions le permettent. Le compilateur est alors en totale conformité avec les références rvalue C\+\+11.  **\(C\+\+11\)**  
  
-   **Héritage des constructeurs** Une classe dérivée peut désormais spécifier qu'elle héritera des constructeurs de sa classe de base \(Base\) en incluant l'instruction à l'aide de l'expression Base::Base; dans sa définition.  Une classe dérivée peut seulement hériter de l'ensemble des constructeurs de sa classe de base. Il n'existe aucun moyen d'hériter uniquement de certains constructeurs de base.  Une classe dérivée ne peut pas hériter de plusieurs classes de base si elle possède des constructeurs ayant une signature identique. Elle ne peut pas non plus définir un constructeur dont la signature est identique à celle de l'un de ses constructeurs hérités.  **\(C\+\+11\)**  
  
-   **Requête Alignment et contrôle** L'alignement d'une variable peut faire l'objet d'une requête à l'aide de l'opérateur alignof\(\) et peut être contrôlé à l'aide du spécificateur alignas\(\).  L'opérateur alignof\(\) renvoie la limite d'octet à laquelle les instances du type doivent être allouées. Pour les références, il renvoie l'alignement du type référencé, et pour les tableaux l'alignement du type élément.  Le spécificateur alignas\(\) contrôle l'alignement d'une variable. Il comporte une constante ou un type, où le type constitue un raccourci pour alignas\(alignof\(type\)\).  **\(C\+\+11\)**  
  
-   **Désallocation dimensionnée** Les variables globales  `void operator delete(void *, std::size_t) noexcept` et `void operator delete[](void *, std::size_t) noexcept` peuvent désormais être surchargées  
  
-   **Élément sizeof étendu** La taille d'une variable de membre de classe ou structure peut désormais être déterminée sans instance de la classe ou structure à l'aide de sizeof\(\). **\(C\+\+11\)**  
  
-   **Attributs** Ils permettent d'étendre la syntaxe de fonctions, de variables, de types et d'autres éléments de programme sans définir de nouveaux mots clés. **\(C\+\+11\)**  
  
-   **constexpr** Créez des variables constantes, des fonctions et des types définis par l'utilisateur au moment de la compilation.  **\(C\+\+11\)**  
  
-   **Littéraux définis par l'utilisateur \(UDL\)** Des suffixes explicites peuvent désormais être ajoutés à des littéraux numériques et de chaîne pour leur conférer une sémantique particulière.  Le compilateur interprète les littéraux contenant un suffixe comme des appels à l'opérateur UDL approprié.  **\(C\+\+11\)**  
  
-   **Statiques « magiques » thread\-safe** Les variables locales statiques sont désormais initialisées de manière thread\-safe, ce qui évite d'avoir recours à une synchronisation manuelle.  Seule l'initialisation est thread\-safe. L'utilisation de variables locales statiques par plusieurs threads doit toujours faire l'objet d'une synchronisation manuelle.  La fonctionnalité de statiques thread\-safe peut être désactivée à l'aide de l'indicateur \/Zc:threadSafeInit pour éviter de créer une dépendance au CRT.  **\(C\+\+11\)**  
  
-   **Stockage thread\-local** Le mot clé thread\_local vous permet de déclarer qu'un objet indépendant doit être créé pour chaque thread.  **\(C\+\+11\)**  
  
-   **noexcept** L'opérateur noexcept peut désormais être utilisé pour voir si une expression lève une exception.  Le spécificateur noexcept peut désormais être utilisé pour spécifier qu'une fonction ne lève pas d'exception.  **\(C\+\+11\)**  
  
-   **Espaces de noms inline** Un espace de noms peut désormais être défini comme inline pour hausser son contenu dans l'espace de noms englobant.  Les espaces de noms inline peuvent être utilisés pour créer des bibliothèques avec version, qui exposent leur version la plus récente par défaut tout en continuant à mettre à disposition les versions d'API précédentes de manière explicite.  **\(C\+\+11\)**  
  
-   **Unions non restreintes** Un type Union peut désormais contenir des types avec des constructeurs non triviaux.  Les constructeurs de ces unions doivent être définis.  **\(C\+\+11\)**  
  
-   **Nouveaux types de caractères et littéraux Unicode** Les littéraux de caractère et de chaîne en UTF\-8, UTF\-16 et UTF\-32 sont désormais pris en charge, et les nouveaux types de caractères char16\_t et char32\_t ont été introduits.  Les littéraux de caractères peuvent comporter un préfixe u8 \(UTF\-8\), u \(UTF\-16\) ou U \(UTF\-32\), par exemple U'a'. Les littéraux de chaînes quant à eux peuvent en plus comporter un préfixe de chaîne brute équivalent u8R \(chaîne brute UTF\-8\), uR \(chaîne brute UTF\-16\) ou UR \(chaîne brute UTF\-32\).  Les noms de caractères universels peuvent être utilisés librement dans les littéraux unicode, par exemple, u'\\u00EF', u8"\\u00EF is i" et u"\\U000000ef is I".  **\(C\+\+11\)**  
  
-   **Séparateurs de chiffre** Des guillemets simples peuvent être insérés à intervalles réguliers pour faciliter la lecture des littéraux numériques longs :  `int x = 1'000'000;` **C\+\+14**  
  
-   **\_\_func\_\_** L'identificateur prédéfini \_\_func\_\_ est défini de manière implicite comme une chaîne contenant le nom non qualifié et sans ornement de la fonction englobante.  
  
-   **\_\_restrict \_\_**L'élément restrict peut désormais être appliqué à des références.  
  
###  <a name="BK_CppStdLib"></a> Bibliothèque standard C\+\+  
  
-   **Littéraux définis par l'utilisateur \(UDL\) pour les types de bibliothèque standard** Les en\-têtes \<chrono\>, \<string\> et \<complex\> fournissent désormais des opérateurs UDL pour vous aider.  Par exemple, 123ms signifie std::chrono::milliseconds\(123\), "hello"s signifie std::string\("hello"\), et 3.14i signifie std::complex\(0.0, 3.14\).  
  
-   **Itérateurs Null Forward** La bibliothèque standard autorise désormais la création d'itérateurs qui ne font pas référence à une instance de conteneur.  Ces itérateurs sont initialisés par une valeur et sont égaux pour un type de conteneur particulier.  La comparaison d'un itérateur initialisé par valeur à un autre qui ne l'est pas n'est pas définie.  **\(C\+\+14\)**  
  
-   **quoted\(\)** La bibliothèque standard prend désormais en charge la fonction quoted\(\) afin de simplifier l'utilisation d'E\/S et de valeurs de chaîne entre guillemets.  Avec la fonction quoted\(\), une chaîne entière entre guillemets est traitée comme une seule entité \(les chaînes de caractères sans espaces étant dans des flux d'E\/S\). De plus, les séquences d'échappement sont conservées lors des opérations d'E\/S.  **\(C\+\+14\)**  
  
-   **Recherche associative hétérogène** La bibliothèque standard prend désormais en charge les fonctions de recherche hétérogène pour les conteneurs associatifs.  Ces fonctions permettent d'effectuer des recherches par type autre que key\_type tant que le type est comparable avec key\_type.  **\(C\+\+14\)**  
  
-   **Séquences d'entiers au moment de la compilation** La bibliothèque standard prend désormais en charge le type integer\_sequence, qui représente une séquence de valeurs entières pouvant être évaluées au moment de la compilation afin de faciliter l'utilisation de packages de paramètres et de simplifier certains modèles de programmation de modèles.  **\(C\+\+14\)**  
  
-   **exchange\(\)** La bibliothèque standard prend désormais en charge la fonction utilitaire std::exchange\(\) pour attribuer une nouvelle valeur à un objet et renvoyer son ancienne valeur.  Pour les types complexes, la fonction exchange\(\) évite d'avoir à copier l'ancienne valeur lorsqu'un constructeur de déplacement est disponible et à copier la nouvelle valeur si elle est temporaire ou déplacée. De plus, elle accepte n'importe quel type comme nouvelle valeur, tirant parti de tout opérateur d'assignation de conversion.  **\(C\+\+14\)**  
  
-   **Fonctions equal\(\), is\_permutation\(\) et mismatch\(\) à deux plages** La bibliothèque standard prend désormais en charge les surcharges pour les éléments std::equal\(\), std::is\_permutation\(\) et std::mismatch\(\) qui acceptent deux plages.  Ces surcharges vérifient que les deux séquences sont de même longueur, ce qui évite au code appelant de le faire. Pour les séquences qui ne prennent pas en charge les conditions requises d'un itérateur aléatoire, ces surcharges vérifient la longueur lors de la comparaison des éléments, gagnant ainsi en efficacité.  **\(C\+\+14\)**  
  
-   **get\<T\>\(\)** La bibliothèque standard prend désormais en charge la fonction de modèle get\<T\>\(\) afin que les éléments tuple puissent être traités par type.  Si un élément tuple contient au moins deux éléments du même type get\<T\>\(\), il ne peut pas être traité par ce type, mais les autres éléments dotés d'un type unique peuvent être traités.  **\(C\+\+14\)**  
  
-   **tuple\_element\_t** La bibliothèque standard prend désormais en charge l'alias de type tuple\_element\_t\<I, T\> qui est un alias de typename tuple\_element\<I, T\>::type.  À l'image des autres alias de type de métafonction dans \<type\_traits\>, il offre un certain confort aux programmeurs de modèles.  **\(C\+\+14\)**  
  
-   **Spécification technique « V3 » du système de fichiers** L'implémentation incluse de la spécification technique du système de fichiers a été mise à jour vers la version 3 de la spécification.  \[N3940\]  
  
-   **Allocateurs minimaux** La bibliothèque standard prend désormais en charge l'interface de l'allocateur minimal. Les principales corrections concernent std::function, shared\_ptr, allocate\_shared\(\) et basic\_string.  **\(C\+\+11\)**  
  
-   **\<chrono\>** Les types chrono high\_resolution\_clock et steady\_clock ont été corrigés.  **\(C\+\+11\)**  
  
-   **N2761 Éléments atomiques des manipulateurs de signal \(C\+\+11\)**  
  
-   **N3922 Nouvelles règles pour auto avec braced\-init\-lists \(C\+\+17\)**  
  
-   **N4051 typename dans les paramètres template template \(C\+\+17\)**  
  
-   **N4259 std::uncaught\_exceptions\(\)**  
  
-   **N4266 Attributs pour espaces de noms et énumérateurs**  
  
-   **N4267 Littéraux de caractère u8**  
  
###  <a name="BK_CRT"></a> Bibliothèque Runtime C  
 **Refactorisation de la bibliothèque CRT** La bibliothèque CRT a été refactorisée en deux parties.  La bibliothèque **Universal CRT** contient le code qui implémente la bibliothèque Runtime C standard.  La bibliothèque vcruntime140.dll \(ou .lib\) contient le code spécifique à la version pour le démarrage du processus et la gestion des exceptions.  La bibliothèque Universal CRT a une API stable. Elle peut donc être utilisée sans modifier le numéro de version dans chaque version de Visual Studio.  Elle est désormais un composant du système d'exploitation Windows traité par Windows Update.  Elle est déjà installé e dans Windows 10.  En utilisant le package redistribuable Visual C\+\+ \(vcredist\), vous pouvez la distribuer avec vos applications pour les versions antérieures de Windows.  
  
 **Conformité à la bibliothèque C99** [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] Implémentation totale de la bibliothèque standard C99, à l'exception de toutes les fonctionnalités de la bibliothèque qui dépendent de fonctionnalités du compilateur non encore prises en charge par le compilateur Visual C\+\+ \(par exemple, \<tgmath.h\> n'est pas implémentée\).  
  
 **Performances** Une grande partie de la bibliothèque a été refactorisée pour rationaliser et simplifier l'utilisation de macros de fichier d'en\-tête.  Cela accélère la compilation et IntelliSense, et améliore la lisibilité.  En outre, de nombreuses fonctions stdio ont été réécrites à la fois pour assurer la conformité aux normes et améliorer les performances.  
  
### Modifications avec rupture  
 Cette prise en charge améliorée des normes ISO C\/C\+\+ peut nécessiter des modifications du code existant afin qu'il soit conforme à C\+\+11 et C99, et qu'il se compile correctement dans Visual Studio 2015.  Pour plus d'informations, consultez [Modifications avec rupture dans Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md).  
  
 La classe concurrency::task et les types associés dans ppltasks.h ne sont plus basés sur le runtime ConcRT.  Ils utilisent désormais le pool de threads Windows comme planificateur.  Cette modification n'affecte que le code qui utilise des primitives de synchronisation ConcRT au sein des opérations concurrency::task.  Ce code doit maintenant utiliser des primitives de synchronisation Windows.  
  
 Les primitives de synchronisation du conteneur STL ne sont plus basées sur ConcRT non plus.  Pour éviter les blocages, n'utilisez pas de primitives de synchronisation STL dans des fonctions telles que **concurrency::parallel\_for** ou avec les types d'agents asynchrones PPL.  
  
##  <a name="BK_FasterBuildTimes"></a> Temps de génération améliorés  
  
-   **Génération de code durant l'édition de liens incrémentielle \(LTCG\)** La liaison incrémentielle peut désormais être utilisée en association avec la génération de code durant l'édition de liens pour réduire le temps de liaison des applications qui utilisent ce type de génération.  Pour activer cette fonctionnalité, utilisez les commutateurs \/LTCG:incremental et \/LTCG:incremental\_rebuild de l'éditeur de liens.  \\  
  
-   **Liens incrémentiels pour les bibliothèques statiques** Les modifications apportées aux bibliothèques statiques auxquelles d'autres modules de code font référence sont désormais liées de façon incrémentielle.  
  
-   **\/Debug:FastLink** Réduit considérablement le temps de liaison grâce à de nouvelles techniques de création PDB.  
  
-   Des améliorations algorithmiques ont été apportées à l'éditeur de liens dans le but de réduire le temps de liaison.  
  
-   Grâce aux améliorations apportées, la génération de code lourd de modèle sera simplifiée.  
  
-   **Optimisation guidée par profil \(PGO\)** Un nouveau mode d'instrumentation léger pour les jeux et les systèmes en temps réel a été introduit dans l'optimisation guidée par profil.  En plus d'autres nouvelles fonctionnalités accessibles via les commutateurs \/GENPROFILE et \/FASTGETPROFILE de l'éditeur de liens, vous pouvez désormais équilibrer la qualité du code et la vitesse de génération lors de l'utilisation de l'optimisation guidée par profil.  
  
-   **Réduction de la taille des fichiers objets** Les améliorations apportées au compilateur et à la bibliothèque standard C\+\+ ont permis de réduire de manière significative la taille des fichiers objets et des bibliothèques statiques.  Ces améliorations n'affectent pas la taille des DLL \(dynamically\-linked libraries\) ou des fichiers exécutables \(exe\), car le code redondant a été supprimé par l'éditeur de liens.  
  
##  <a name="BK_PerfCodeQuality"></a> Performances et qualité du code  
  
-   **Amélioration de la vectorisation automatique** Inclut désormais la vectorisation du flux de contrôle \(if\-then\-else\) et la vectorisation lors de la compilation sous \/O1 \(Réduire la taille\). Des améliorations ont également été apportées à la qualité générale du code de vecteur, notamment la prise en charge du STL parallèle, de la vectorisation de boucles « more range\-based for », et de la boucle \#pragma loop\(ivdep\).  
  
-   **Amélioration de l'optimisation scalaire** Génération de code améliorée pour les opérations bit\-test, optimisation et fusion du flux de contrôle, \(commutation loop\-if\) et autres optimisations scalaires \(par exemple, génération de code améliorée pour std::min et std::max\).  
  
-   **Optimisation guidée par profil \(PGO\)** Un certain nombre d'améliorations ont été apportées à l'optimisation guidée par profil, notamment les ensembles de référence, les capacités de disposition des données, et la possibilité de réutiliser des décisions précédentes relatives à l'incorporation,  à l'opposition vitesse\/taille et à la disposition.  
  
##  <a name="BK_IDE"></a> Productivité, débogage et diagnostics  
  
###  <a name="BK_SingleFileIntelliSense"></a> IntelliSense avec un fichier unique  
 Vous avez accès à IntelliSense quand vous ouvrez un fichier de code source unique dans l'éditeur, sans avoir à ouvrir un fichier de projet.  
  
###  <a name="BK_Refactoring"></a> Refactorisation  
 Nous avons ajouté les fonctionnalités suivantes à la prise en charge de la refactorisation pour C\+\+ :  
  
-   **Renommer un symbole** Modifie toutes les occurrences d'un symbole.  
  
-   **Fonction d'extraction** Déplace le code sélectionné au sein de sa fonction.  Cette refactorisation est disponible en tant qu'extension de Visual Studio dans la galerie Visual Studio.  
  
-   **Implémenter des fonctions virtuelles pures** Génère des définitions de fonction pour les fonctions virtuelles pures héritées par une classe ou structure.  Les héritages multiples et récursifs sont pris en charge.  Activez cette refactorisation à partir de la définition de classe qui hérite pour implémenter toutes les fonctions virtuelles pures héritées, ou à partir d'un spécificateur de classe de base pour implémenter les fonctions virtuelles pures de la classe de base concernée uniquement.  
  
-   **Créer une déclaration ou une définition** Génère une déclaration à partir d'une définition existante, ou une définition par défaut à partir d'une déclaration existante.  Accédez à cette refactorisation à partir de la déclaration ou définition existante, ou à partir de l'indicateur LightBulb.  
  
-   **Déplacer la définition de fonction** Déplace le corps d'une fonction entre le code source et les fichiers d'en\-tête.  Activez cette refactorisation à partir de la signature de la fonction.  
  
-   **Convertir en littéral de chaîne brute** Convertit une chaîne contenant des séquences d'échappement en littéral de chaîne brute.  Les séquences d'échappement prises en charge sont \\\\ \(barre oblique inverse\), \\n \(nouvelle ligne\), \\t \(tabulation\), \\' \(apostrophe\), \\ "\(guillemets doubles\) et \\?  \(point d'exclamation\).  Activez cette fonctionnalité en cliquant avec le bouton droit à l'intérieur d'une chaîne.  
  
 Afin d'améliorer la fonctionnalité Rechercher dans les fichiers, les résultats suivants peuvent désormais être ajoutés aux résultats précédents. Les résultats accumulés peuvent être supprimés.  
  
 **Amélioration de la lisibilité IntelliSense** Pour faciliter la lecture des instanciations de modèle et typedefs complexes, l'aide et les informations express relatives aux paramètres ont été simplifiées.  
  
###  <a name="BK_PDB"></a> Améliorations de la base de données du programme  
  
-   La vitesse de l'analyse de solution a été améliorée, notamment pour les solutions volumineuses.  
  
-   Les opérations telles que Go To Definition ne sont plus bloquées lors de l'analyse de solution, sauf lors de la première analyse suivant la première ouverture d'une solution.  
  
##  <a name="BK_Diagnostics"></a> Diagnostics  
  
1.  **Visualisations du débogueur** Ajoutez des visualisations de débogueur Natvis à votre projet Visual Studio pour une intégration du contrôle source et une gestion simplifiées.  Des fichiers Natvis peuvent être modifiés et enregistrés pendant une session de débogage et le débogueur récupère automatiquement les modifications.  Pour plus d'informations, consultez le [billet de blog](http://blogs.msdn.com/b/vcblog/archive/2014/06/12/project-support-for-natvis.aspx).  
  
2.  **Diagnostics de mémoire native**  
  
    1.  Des **sessions de diagnostic de mémoire** \(Ctrl\+Alt\+F2\) vous permettent de contrôler en direct l'utilisation de mémoire par votre application native pendant une session de débogage.  
  
    2.  Des **instantanés de mémoire** capturent une image momentanée du contenu du tas de votre application.  Vous pouvez comparer deux instantanés de mémoire pour examiner les différences d'état du tas.  Vous pouvez afficher les types d'objets, les valeurs d'instance et les piles d'appel d'allocation pour chaque instance une fois l'application arrêtée.  Afficher l'arborescence des appels par frame de pile pour chaque instantané.  
  
3.  **Amélioration de la détection de blocage et de la reprise** lors de l'appel de fonctions C\+\+ à partir des fenêtres Espion et Exécution.  
  
4.  **Amélioration des diagnostics du compilateur** Le compilateur fournit des avertissements améliorés sur le code suspect.  De nouveaux avertissements ont été ajoutés \(par exemple, les variables ombrées et les chaînes de format printf incompatibles\).  Les messages d'avertissement existants sont désormais plus clairs.  
  
5.  **Indicateur \/Wv** Les avertissements introduits après une version XX.YY.ZZZZ de compilateur spécifique peuvent être désactivés à l'aide de l'indicateur \/Wv:XX.YY.ZZZZ.  D'autres avertissements peuvent être désactivés de manière spécifique en plus de ceux spécifiés via l'indicateur \/Wv.  
  
6.  **Prise en charge améliorée pour le code optimisé de débogage** Le code de débogage comportant les indicateurs \/Zi, \/Zo ou \/Z7 est activé.  
  
##  <a name="BK_Win10"></a> Ciblage de Windows 10  
 Visual Studio prend désormais en charge le ciblage de Windows 10 dans C\+\+.  De nouveaux modèles de projet pour le développement d'applications Windows universelles prennent en charge le ciblage des appareils Windows 10 tels que les ordinateurs de bureau, les téléphones portables, les tablettes, HoloLens et autres appareils.  Pour plus d'informations, consultez [Créer une application « hello world » dans Windows 10](https://msdn.microsoft.com/en-us/library/windows/apps/dn996906.aspx).  
  
##  <a name="BK_GraphicsDiagnostics"></a> Graphics Diagnostics  
 Graphics Diagnostics a été amélioré par le biais des fonctionnalités suivantes :  
  
-   **Prise en charge de Graphics Diagnostics pour DirectX12.** L'outil Graphics Diagnostics de Visual Studio prend désormais en charge les problèmes de rendu du débogage dans les applications DirectX12.  
  
-   **Capture consécutive** Capturez jusqu'à 30 images consécutives en une fois.  
  
-   **Capture programmée** Démarrez une capture d'image par programmation.  La capture programmée permet notamment de déboguer des nuanceurs de calcul dans les programmes qui n'appellent jamais Présent, ou lorsqu'un problème de rendu est difficile à capturer manuellement mais peut être prédit par programmation à partir de l'état de l'application au moment de l'exécution.  
  
-   **Liste d'événements graphiques améliorée** Une nouvelle vue Appels de dessin permet d'afficher les événements capturés ainsi que leur état dans une hiérarchie organisée par appels de dessin.  Vous pouvez développer les appels de dessin pour afficher l'état de l'appareil au moment de l'appel, et développer encore chaque état pour afficher les événements qui définissent leurs valeurs.  
  
-   **Prise en charge pour Windows Phone 8.1** Graphics Diagnostics prend désormais en charge le débogage d'applications Windows Phone 8.1 dans l'émulateur Windows Phone ou sur le Windows Phone attaché.  
  
-   **Analyse de frames graphiques** Cet outil collecte les mesures de performances sur les images capturées. Il effectue également un ensemble d'expériences prédéfinies qui fournissent des informations sur l'impact de l'application de diverses techniques sur les performances.  L'analyse de frames collecte également les compteurs de performances à partir du matériel.  
  
-   **Interface utilisateur dédiée pour l'analyse graphique** La nouvelle fenêtre Analyseur graphique de Visual Studio est un espace de travail dédié pour l'analyse de frames graphiques.  
  
-   **Modification et application de nuanceurs** Examinez l'impact des modifications apportées au code du nuanceur dans un journal capturé sans avoir à réexécuter l'application.  
  
-   Configurez les options de capture sous Outils\-\>Options\-\>Graphics Diagnostics.  
  
-   Outil de ligne de commande pour la capture et la lecture d'images.  
  
 Pour plus d'informations, consultez [Graphics Diagnostics \(débogage DirectX Graphics\)](../Topic/Visual%20Studio%20Graphics%20Diagnostics.md).  
  
##  <a name="BK_GPUUsage"></a> Nouvel outil d'utilisation du GPU  
 L'outil d'utilisation du GPU dans Visual Studio 2015 permet de comprendre l'utilisation de GPU par les applications DirectX.  Les graphiques concernant la durée de frame, la fréquence d'images et l'utilisation du GPU sont disponibles pendant l'exécution des applications.  De plus, en recueillant et en analysant des données d'utilisation du GPU détaillées, cet outil fournit des informations sur la durée d'exécution du processeur et du GPU pour des événements DirectX individuels. Par conséquent, il peut être utile pour déterminer si le goulot d'étranglement de performances est le processeur ou le GPU.  Consultez [Utilisation du GPU](../Topic/GPU%20Usage.md).  
  
##  <a name="BK_MFC"></a> Nouvelles fonctionnalités MFC  
 Vous pouvez désormais spécifier comment les contrôles sont redimensionnés et déplacés automatiquement quand un utilisateur modifie la taille d'une boîte de dialogue.  Pour plus d'informations, consultez [Disposition dynamique](../mfc/dynamic-layout.md)  
  
## Voir aussi  
 [Nouveautés de Visual Studio 2015](../Topic/What's%20New%20in%20Visual%20Studio%202015.md)   
 [Blog de l'équipe Visual C\+\+](http://blogs.msdn.com/b/vcblog/)