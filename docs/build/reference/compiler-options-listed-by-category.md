---
title: "Options du compilateur class&#233;es par cat&#233;gorie | Microsoft Docs"
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
  - "options du compilateur, C++"
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
caps.latest.revision: 64
caps.handback.revision: 64
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Options du compilateur class&#233;es par cat&#233;gorie
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet article contient une liste par catégorie d'options du compilateur. Pour obtenir une liste alphabétique, consultez [Options du compilateur classées par ordre alphabétique](../../build/reference/compiler-options-listed-alphabetically.md).  
  
### Optimisation  
  
|Option|Objectif|  
|------------|--------------|  
|[\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Crée un code compact.|  
|[\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Crée un code rapide.|  
|[\/Ob](../../build/reference/ob-inline-function-expansion.md)|Contrôle l'expansion inline.|  
|[\/Od](../../build/reference/od-disable-debug.md)|Désactive l'optimisation.|  
|[\/Og](../../build/reference/og-global-optimizations.md)|Obsolète. Utilise des optimisations globales.|  
|[\/Oi](../../build/reference/oi-generate-intrinsic-functions.md)|Génère des fonctions intrinsèques.|  
|[\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Favorise la taille du code.|  
|[\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Favorise la vitesse du code.|  
|[\/Ox](../../build/reference/ox-full-optimization.md)|Utilise l'optimisation maximale \(\/Ob2gity \/Gs\).|  
|[\/Oy](../../build/reference/oy-frame-pointer-omission.md)|Omet le pointeur de frame. \(x86 uniquement\)|  
|[\/favor](../../build/reference/favor-optimize-for-architecture-specifics.md)|Produit du code optimisé pour une architecture spécifiée ou pour une plage d'architectures.|  
  
### Génération de code  
  
|Option|Objectif|  
|------------|--------------|  
|[\/arch](../../build/reference/arch-x86.md)|Utiliser des instructions SSE ou SSE2 dans la génération du code. \(x86 uniquement\)|  
|[\/clr](../../build/reference/clr-common-language-runtime-compilation.md)|Produit un fichier de sortie à exécuter sur le CLR \(Common Language Runtime\).|  
|[\/EH](../../build/reference/eh-exception-handling-model.md)|Spécifie le modèle de gestion des exceptions.|  
|[\/fp](../../build/reference/fp-specify-floating-point-behavior.md)|Spécifie le comportement de virgule flottante.|  
|[\/GA](../../build/reference/ga-optimize-for-windows-application.md)|Optimise pour les applications Windows.|  
|[\/Gd](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Utilise la convention d'appel `__cdecl`. \(x86 uniquement\)|  
|[\/Ge](../../build/reference/ge-enable-stack-probes.md)|Obsolète. Active les tests de pile.|  
|[\/GF](../../build/reference/gf-eliminate-duplicate-strings.md)|Active le regroupement des chaînes.|  
|[\/Gh](../../build/reference/gh-enable-penter-hook-function.md)|Appelle la fonction de raccordement `_penter`.|  
|[\/GH](../../build/reference/gh-enable-pexit-hook-function.md)|Appelle la fonction de raccordement `_pexit`.|  
|[\/GL](../../build/reference/gl-whole-program-optimization.md)|Active l'optimisation de l'ensemble du programme.|  
|[\/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|Active la régénération minimale.|  
|[\/GR](../../build/reference/gr-enable-run-time-type-information.md)|Active les informations de type au moment de l'exécution \(RTTI, Run\-Time Type Information\).|  
|[\/Gr](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Utilise la convention d'appel `__fastcall`. \(x86 uniquement\)|  
|[\/GS](../../build/reference/gs-buffer-security-check.md)|Vérifie la sécurité des mémoires tampons.|  
|[\/Gs](../../build/reference/gs-control-stack-checking-calls.md)|Gère les tests de pile.|  
|[\/GT](../../build/reference/gt-support-fiber-safe-thread-local-storage.md)|Prend en charge la sécurité des fibres pour les données allouées en utilisant un stockage local des threads de type statique.|  
|[\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)|Ajoute des vérifications de sécurité de protection du flux de contrôle.|  
|[\/Gv](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Utilise la convention d'appel `__vectorcall`. \(x86 et x64 uniquement\)|  
|[\/Gw](../../build/reference/gw-optimize-global-data.md)|Active l'optimisation globale des données de la totalité du programme.|  
|[\/GX](../../build/reference/gx-enable-exception-handling.md)|Obsolète. Active la gestion synchrone des exceptions. Utilisez [\/EH](../../build/reference/eh-exception-handling-model.md) à la place.|  
|[\/Gy](../../build/reference/gy-enable-function-level-linking.md)|Active la liaison au niveau des fonctions.|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Obsolète. Active les vérifications rapides. \(Identique à [\/RTC1](../../build/reference/rtc-run-time-error-checks.md)\)|  
|[\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Utilise la convention d'appel `__stdcall`. \(x86 uniquement\)|  
|[\/homeparams](../../build/reference/homeparams-copy-register-parameters-to-stack.md)|Force l'écriture des paramètres passés dans les registres à leurs emplacements sur la pile lors de l'entrée de la fonction. Cette option du compilateur est uniquement destinée aux compilateurs [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] \(compilation native et croisée\).|  
|[\/hotpatch](../../build/reference/hotpatch-create-hotpatchable-image.md)|Crée une image corrigeable en mémoire.|  
|[\/Qfast\_transcendentals](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md)|Génère des fonctions transcendantes rapides.|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|Obsolète. Supprime l'appel de la fonction d'assistance `_ftol` quand la conversion d'un type à virgule flottante vers un type intégral est requise. \(x86 uniquement\)|  
|[\/Qimprecise\_fwaits](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Supprime les commandes `fwait` dans les blocs `try`.|  
|[\/Qpar](../../build/reference/qpar-auto-parallelizer.md)|Active la parallélisation automatique des boucles.|  
|[\/Qpar\-report](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)|Active les niveaux de création de rapports pour la parallélisation automatique.|  
|[\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md)|Utilise des instructions de déplacement d'entiers pour les valeurs à virgule flottante et désactive certaines optimisations de charge de virgule flottante.|  
|[\/Qvec\-report \(Niveau de rapport du vectoriseur automatique\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)|Active les niveaux de création de rapports pour le vectorisation automatique.|  
|[\/RTC](../../build/reference/rtc-run-time-error-checks.md)|Active les vérifications des erreurs au moment de l'exécution.|  
|[\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)|Sélectionne comment le mot clé volatile est interprété.|  
  
### Fichiers de sortie  
  
|Option|Objectif|  
|------------|--------------|  
|[\/doc](../../build/reference/doc-process-documentation-comments-c-cpp.md)|Traite les commentaires de documentation pour les diriger vers un fichier XML.|  
|[\/FA](../../build/reference/fa-fa-listing-file.md)|Configure un fichier de listes d'assemblys.|  
|[\/Fa](../../build/reference/fa-fa-listing-file.md)|Crée un fichier de listes d'assemblys.|  
|[\/Fd](../../build/reference/fd-program-database-file-name.md)|Renomme le fichier de base de données du programme.|  
|[\/Fe](../../build/reference/fe-name-exe-file.md)|Renomme le fichier exécutable.|  
|[\/FI](../../build/reference/fi-preprocess-output-file-name.md)|Spécifie le nom du fichier de sortie prétraité.|  
|[\/Fm](../../build/reference/fm-name-mapfile.md)|Crée un fichier de mappage.|  
|[\/Fo](../../build/reference/fo-object-file-name.md)|Crée un fichier objet.|  
|[\/Fp](../../build/reference/fp-name-dot-pch-file.md)|Spécifie un nom de fichier d'en\-tête précompilé.|  
|[\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Génère des fichiers browser.|  
  
### Préprocesseur  
  
|Option|Objectif|  
|------------|--------------|  
|[\/AI](../../build/reference/ai-specify-metadata-directories.md)|Spécifie un répertoire à explorer afin de résoudre les références de fichiers passées à la directive [\#using](../../preprocessor/hash-using-directive-cpp.md).|  
|[\/C](../../build/reference/c-preserve-comments-during-preprocessing.md)|Conserve les commentaires pendant le prétraitement.|  
|[\/D](../../build/reference/d-preprocessor-definitions.md)|Définit des constantes et des macros.|  
|[\/E](../../build/reference/e-preprocess-to-stdout.md)|Copie la sortie du préprocesseur vers une sortie standard.|  
|[\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|Copie la sortie du préprocesseur vers une sortie standard.|  
|[\/FI](../../build/reference/fi-name-forced-include-file.md)|Prétraite le fichier Include spécifié.|  
|[\/FU](../../build/reference/fu-name-forced-hash-using-file.md)|Force l'utilisation d'un nom de fichier, comme s'il avait été passé à la directive [\#using](../../preprocessor/hash-using-directive-cpp.md).|  
|[\/Fx](../../build/reference/fx-merge-injected-code.md)|Fusionne le code injecté avec le fichier source.|  
|[\/I](../../build/reference/i-additional-include-directories.md)|Recherche des fichiers Include dans un répertoire.|  
|[\/P](../../build/reference/p-preprocess-to-a-file.md)|Écrit la sortie du préprocesseur dans un fichier.|  
|[\/U](../../build/reference/u-u-undefine-symbols.md)|Supprime une macro prédéfinie.|  
|[\/u](../../build/reference/u-u-undefine-symbols.md)|Supprime toutes les macros prédéfinies.|  
|[\/X](../../build/reference/x-ignore-standard-include-paths.md)|Ignore le répertoire Include standard.|  
  
### Langage  
  
|Option|Objectif|  
|------------|--------------|  
|[\/openmp](../../build/reference/openmp-enable-openmp-2-0-support.md)|Active [\#pragma omp](../../preprocessor/omp.md) dans le code source.|  
|[\/vd](../../build/reference/vd-disable-construction-displacements.md)|Supprime ou active les membres masqués de la classe `vtordisp`.|  
|[\/vmb](../../build/reference/vmb-vmg-representation-method.md)|Utilise la meilleure base pour les pointeurs vers des membres.|  
|[\/vmg](../../build/reference/vmb-vmg-representation-method.md)|Utilise la généralité complète pour les pointeurs vers des membres.|  
|[\/vmm](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Déclare un héritage multiple.|  
|[\/vms](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Déclare un héritage simple.|  
|[\/vmv](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Déclare un héritage virtuel.|  
|[\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)|Génère des informations de débogage compatibles C 7.0.|  
|[\/Za](../../build/reference/za-ze-disable-language-extensions.md)|Désactive les extensions de langage.|  
|[\/Zc](../../build/reference/zc-conformance.md)|Spécifie le comportement standard sous [\/Ze](../../build/reference/za-ze-disable-language-extensions.md).|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Obsolète. Active les extensions de langage.|  
|[\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)|Inclut des informations de débogage dans une base de données du programme compatible avec Modifier & Continuer. \(x86 uniquement\)|  
|[\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)|Génère des informations de débogage complètes.|  
|[\/Zl](../../build/reference/zl-omit-default-library-name.md)|Supprime le nom de la bibliothèque par défaut du fichier .obj.|  
|[\/Zp](../../build/reference/zp-struct-member-alignment.md) *n*|Compresse les membres de la structure.|  
|[\/Zs](../../build/reference/zs-syntax-check-only.md)|Vérifie la syntaxe uniquement.|  
|[\/ZW](../../build/reference/zw-windows-runtime-compilation.md)|Produit un fichier de sortie à exécuter sur [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].|  
  
### Liaison  
  
|Option|Objectif|  
|------------|--------------|  
|[\/F](../../build/reference/f-set-stack-size.md)|Définit la taille de la pile.|  
|[\/LD](../../build/reference/md-mt-ld-use-run-time-library.md)|Crée une bibliothèque de liens dynamiques.|  
|[\/LDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Crée une bibliothèque de liens dynamiques de débogage.|  
|[\/link](../../build/reference/link-pass-options-to-linker.md)|Passe l'option spécifiée à LINK.|  
|[\/LN](../../build/reference/ln-create-msil-module.md)|Crée un module MSIL.|  
|[\/MD](../../build/reference/md-mt-ld-use-run-time-library.md)|Compile pour créer une DLL multithread, à l'aide de MSVCRT.lib.|  
|[\/MDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Compile pour créer une DLL multithread de débogage, à l'aide de MSVCRTD.lib.|  
|[\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)|Compile pour créer un fichier exécutable multithread, à l'aide de LIBCMT.lib.|  
|[\/MTd](../../build/reference/md-mt-ld-use-run-time-library.md)|Compile pour créer un fichier exécutable multithread de débogage, à l'aide de LIBCMTD.lib.|  
  
### En\-tête précompilé  
  
|Option|Objectif|  
|------------|--------------|  
|[\/Y\-](../../build/reference/y-ignore-precompiled-header-options.md)|Ignore toutes les autres options d'en\-tête précompilé pour la génération en cours.|  
|[\/Yc](../../build/reference/yc-create-precompiled-header-file.md)|Crée un fichier d'en\-tête précompilé.|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Place des informations de débogage complètes dans tous les fichiers objets.|  
|[\/Yu](../../build/reference/yu-use-precompiled-header-file.md)|Utilise un fichier d'en\-tête précompilé pendant la génération.|  
  
### Divers  
  
|Option|Objectif|  
|------------|--------------|  
|[\/?](../../build/reference/help-compiler-command-line-help.md)|Affiche la liste des options du compilateur.|  
|[@](../../build/reference/at-specify-a-compiler-response-file.md)|Spécifie un fichier réponse.|  
|[\/analyze](../../build/reference/analyze-code-analysis.md)|Active l'analyse du code.|  
|[\/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)|Augmente le nombre de sections adressables dans un fichier .obj.|  
|[\/c](../../build/reference/c-compile-without-linking.md)|Compile sans liaison.|  
|[\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md)|Spécifie le nombre de threads de cl.exe à utiliser pour l'optimisation et la génération de code.|  
|[\/errorReport](../../build/reference/errorreport-report-internal-compiler-errors.md)|Vous permet de signaler les erreurs internes du compilateur \(ICE\) directement à l'équipe Visual C\+\+.|  
|[\/FC](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)|Affiche le chemin d'accès complet des fichiers de code source passés à cl.exe dans un texte de diagnostic.|  
|[\/FS](../../build/reference/fs-force-synchronous-pdb-writes.md)|Force la sérialisation des écritures dans le fichier de base de données de programme \(PDB\) via MSPDBSRV.EXE.|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|Obsolète. Limite la longueur des noms externes \(publics\).|  
|[\/HELP](../../build/reference/help-compiler-command-line-help.md)|Affiche la liste des options du compilateur.|  
|[\/J](../../build/reference/j-default-char-type-is-unsigned.md)|Change le type `char` par défaut.|  
|[\/kernel](../../build/reference/kernel-create-kernel-mode-binary.md)|Le compilateur et l'éditeur de liens créeront un binaire qui peut être exécuté dans le noyau Windows.|  
|[\/MP](../../build/reference/mp-build-with-multiple-processes.md)|Génère plusieurs fichiers sources simultanément.|  
|[\/nologo](../../build/reference/nologo-suppress-startup-banner-c-cpp.md)|Supprime l'affichage de la bannière d'ouverture de session.|  
|[\/sdl](../../build/reference/sdl-enable-additional-security-checks.md)|Active des fonctionnalités de sécurité et ses avertissements supplémentaires.|  
|[\/showIncludes](../../build/reference/showincludes-list-include-files.md)|Affiche la liste de tous les fichiers Include pendant la compilation.|  
|[\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) [\/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Spécifie un fichier source C.|  
|[\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) [\/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Spécifie un fichier source C\+\+.|  
|[\/V](../../build/reference/v-version-number.md)|Obsolète. Définit la chaîne version.|  
|[\/w](../../build/reference/compiler-option-warning-level.md)|Désactive tous les avertissements.|  
|[\/W0, \/W1, \/W2, \/W3, \/W4](../../build/reference/compiler-option-warning-level.md)|Définit le niveau d’avertissement de sortie.|  
|[\/w1, \/w2, \/w3, \/w4](../../build/reference/compiler-option-warning-level.md)|Définit le niveau de l’avertissement spécifié.|  
|[\/Wall](../../build/reference/compiler-option-warning-level.md)|Active tous les avertissements, y compris les avertissements qui sont désactivés par défaut.|  
|[\/wd](../../build/reference/compiler-option-warning-level.md)|Désactive l’avertissement spécifié.|  
|[\/we](../../build/reference/compiler-option-warning-level.md)|Traite l’avertissement spécifié comme une erreur.|  
|[\/WL](../../build/reference/wl-enable-one-line-diagnostics.md)|Active un diagnostic de ligne pour les messages d'erreur et d'avertissement lors de la compilation du code source C\+\+ à partir de la ligne de commande.|  
|[\/wo](../../build/reference/compiler-option-warning-level.md)|Affiche l’avertissement spécifié une seule fois.|  
|[\/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md)|Obsolète. Détecte les problèmes de portabilité 64 bits.|  
|[\/Wv](../../build/reference/compiler-option-warning-level.md)|Désactive les avertissements introduits par les versions ultérieures du compilateur.|  
|[\/WX](../../build/reference/compiler-option-warning-level.md)|Traite les avertissements comme des erreurs.|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Obsolète. Place des informations de débogage complètes dans tous les fichiers objets. Utilisez [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) à la place.|  
|[\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)|Injecte une référence PCH lors de la création d'une bibliothèque de débogage.|  
|[\/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)|Spécifie la limite d'allocation de mémoire de l'en\-tête précompilé.|  
  
### Options du compilateur déconseillées et supprimées  
  
|Option|Objectif|  
|------------|--------------|  
|[\/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md)|Obsolète. Utilisez plutôt [\/LN \(Créer le module MSIL\)](../../build/reference/ln-create-msil-module.md).|  
|[\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Obsolète. Crée un fichier d’informations de consultation sans variables locales.|  
|[\/Ge](../../build/reference/ge-enable-stack-probes.md)|Obsolète. Active les tests de pile. Activé par défaut.|  
|[\/GX](../../build/reference/gx-enable-exception-handling.md)|Obsolète. Active la gestion synchrone des exceptions. Utilisez [\/EH](../../build/reference/eh-exception-handling-model.md) à la place.|  
|[\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Obsolète. Active les vérifications rapides. Utilisez [\/RTC1](../../build/reference/rtc-run-time-error-checks.md) à la place.|  
|[\/H](../../build/reference/h-restrict-length-of-external-names.md)|Obsolète. Limite la longueur des noms externes \(publics\).|  
|[\/Og](../../build/reference/og-global-optimizations.md)|Obsolète. Utilise des optimisations globales.|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|Obsolète. Était utilisé pour spécifier le mode de conversion d’un type à virgule flottante en type intégral.|  
|[\/V](../../build/reference/v-version-number.md)|Obsolète. Définit la chaîne de version du fichier .obj.|  
|[\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Obsolète. Place des informations de débogage complètes dans tous les fichiers objets. Utilisez [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) à la place.|  
|[\/Zc:forScope\-](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)|Obsolète. Désactive la conformité dans la portée d’une boucle for.|  
|[\/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Obsolète. Active les extensions de langage.|  
|[\/Zg](../../build/reference/zg-generate-function-prototypes.md)|Supprimé dans Visual C\+\+ 2015. Génère des prototypes de fonction.|  
  
## Voir aussi  
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)