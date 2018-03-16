---
title: "Guide pratique pour signaler un problème avec l’ensemble d’outils Visual C++ | Microsoft Docs"
ms.date: 1/11/2018
ms.technology:
- cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd7ba80e60251c56fd28a1c380d395e686fc27a4
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset"></a>Guide pratique pour signaler un problème avec l’ensemble d’outils Visual C++

Si vous rencontrez des problèmes avec le compilateur Microsoft Visual C++, l’éditeur de liens ou autres outils et bibliothèques, nous aimerions les connaître.

La meilleure façon de nous informer d’un problème consiste à nous envoyer un rapport qui inclut une description du problème que vous avez rencontré, des informations sur la façon dont vous générez votre programme et une *reproduction* qui nous servira à reproduire le problème sur nos propres ordinateurs. Ces informations nous permettent de vérifier rapidement que le problème existe dans notre code et qu’il n’est pas propre à votre environnement, de déterminer s’il affecte d’autres versions du compilateur et de diagnostiquer sa cause.

Dans ce document, vous obtiendrez plus d’informations sur les procédures suivantes

- [Comment préparer votre rapport](#how-to-prepare-your-report) et les éléments essentiels à un bon rapport.

- [Comment générer une reproduction](#how-to-generate-a-repro) et les différents types de reproductions.

- [Modes d’envoi de votre rapport](#ways-to-send-your-report) et leurs différences.

Vos rapports sont importants pour nous ainsi que pour d’autres développeurs comme vous. Merci de nous aider à améliorer Visual C++ !

## <a name="how-to-prepare-your-report"></a>Comment préparer votre rapport

Il est important de créer un rapport de qualité, car il est très difficile de reproduire le problème rencontré sur nos propres ordinateurs sans informations complètes. Plus votre rapport est exhaustif, plus nous serons en mesure de recréer et diagnostiquer le problème efficacement.

Au minimum, votre rapport doit contenir les éléments suivants :

- Informations sur la version complète de l’ensemble d’outils que vous utilisez.

- Ligne de commande cl.exe complète utilisée pour générer votre code.

- Description détaillée du problème rencontré.

- Une reproduction est un exemple de code source simplifié et autonome qui illustre le problème.

Poursuivez votre lecture pour en savoir plus sur les informations spécifiques dont nous avons besoin, l’endroit où vous pouvez les trouver et la façon de créer une bonne reproduction.

### <a name="the-toolset-version"></a>Version de l’ensemble d’outils

Nous avons besoin d’informations complètes sur la version et l’architecture cible de l’ensemble d’outils qui entraînent le problème pour pouvoir tester votre reproduction avec le même ensemble d’outils sur nos ordinateurs. Si nous pouvons reproduire le problème, ces informations nous donnent également un point de départ pour rechercher si d’autres versions de l’ensemble d’outils présentent le même problème.

#### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>Pour indiquer la version complète du compilateur que vous utilisez

1. Ouvrez l’**invite de commandes développeur** qui correspond à l’architecture de configuration et à la version de Visual Studio utilisées pour générer votre projet. Par exemple, si vous générez vos projets en utilisant Visual Studio 2017 sur x64 pour des cibles x64, choisissez **Invite de commandes des outils natifs x64 pour VS 2017**. Pour plus d’informations, consultez [Raccourcis de l’invite de commandes développeur](build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

1. Dans la fenêtre de console de l’invite de commandes développeur, entrez la commande **cl**.

La sortie doit ressembler à ceci :

```Output
C:\Users\username\Source>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x64
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

Copiez et collez l’intégralité de la sortie dans votre rapport.

### <a name="the-command-line"></a>Ligne de commande

Nous avons besoin de la ligne de commande exacte (cl.exe et tous ses arguments) utilisée pour générer votre code afin de pouvoir le générer exactement de la même façon sur nos ordinateurs. Ce point est important, car le problème que vous avez rencontré peut uniquement se produire lors de la génération avec un certain argument ou une certaine combinaison d’arguments.

L’endroit le plus approprié pour trouver ces informations se situe dans le journal de génération immédiatement après avoir rencontré le problème. Cela permet de garantir que la ligne de commande contient exactement les mêmes arguments pouvant contribuer au problème.

#### <a name="to-report-the-contents-of-the-command-line"></a>Pour signaler le contenu de la ligne de commande

1. Recherchez le fichier **CL.command.1.tlog** et ouvrez-le. Par défaut, ce fichier se trouve dans votre dossier Documents dans \\Visual Studio *version*\\Projets\\*NomSolution*\\*NomProjet*\\*Configuration*\\*NomProjet*.tlog\\CL.command.1.tlog ou dans votre dossier Utilisateur sous \\Source\\Référentiels\\*NomSolution*\\*NomProjet*\\*Configuration*\\*NomProjet*.tlog\\CL.command.1.tlog. Il peut se trouver dans un autre emplacement si vous utilisez un autre système de build ou si vous avez changé l’emplacement par défaut de votre projet.

   Dans ce fichier, vous trouverez les noms des fichiers de code source suivis des arguments de ligne de commande utilisés pour les compiler, chacun sur une ligne distincte.

1. Recherchez la ligne qui contient le nom du fichier de code source dans lequel le problème se produit ; la ligne en dessous contient les arguments de la commande cl.exe correspondants.

Copiez et collez l’intégralité de la ligne de commande dans votre rapport.

### <a name="a-description-of-the-problem"></a>Description du problème

Nous avons besoin d’une description détaillée du problème que vous avez rencontré pour pouvoir vérifier que nous constatons le même effet sur nos ordinateurs ; il nous est également parfois utile de savoir ce que vous tentiez d’effectuer et ce à quoi vous vous attendiez.

Fournissez les messages d’erreur exacts que vous recevez de l’ensemble d’outils ou le comportement d’exécution exact que vous voyez. Nous avons besoin de ces informations pour vérifier que nous avons correctement reproduit le problème. Incluez l’intégralité de la sortie du compilateur, pas juste le dernier message d’erreur. Nous devons voir tout ce qui a conduit au problème que vous signalez. Si vous pouvez dupliquer le problème avec le compilateur de ligne de commande, cette sortie du compilateur est préférable. En effet, l’IDE et autres systèmes de build peuvent filtrer les messages d’erreur que vous voyez ou capturer uniquement la première ligne d’un message d’erreur.

Si le problème vient du compilateur qui accepte du code non valide et ne génère pas de diagnostic, notez ce point dans votre rapport.

Pour signaler un problème de comportement d’exécution, ajoutez une copie exacte de ce que le programme envoie et de ce que vous vous attendez à voir. Dans l’idéal, c’est incorporé dans l’instruction de sortie elle-même, par exemple, `printf("This should be 5: %d\n", actual_result);`. Si votre programme plante ou se bloque, mentionnez-le également.

Ajoutez tout autre détail susceptible de nous aider à diagnostiquer le problème que vous rencontrez, comme des solutions de contournement éventuellement trouvées. Évitez de répéter des informations qui figurent ailleurs dans votre rapport.

### <a name="the-repro"></a>Reproduction

Une reproduction est un exemple de code source complet et autonome qui reproduit le problème que vous avez rencontré (d’où son nom). Nous avons besoin d’une reproduction pour pouvoir reproduire l’erreur sur nos ordinateurs. Le code doit être suffisant en lui-même pour créer un exécutable simple qui se compile et s’exécute, ou qui aurait dû se compiler et s’exécuter si vous n’aviez pas rencontré de problème. Une reproduction n’est pas un extrait de code ; elle doit avoir des classes et des fonctions complètes et contenir toutes les directives #include, même pour les en-têtes standard.

#### <a name="what-makes-a-good-repro"></a>Ce qui constitue une bonne reproduction

Une bonne reproduction est :

- **Est minimale.** Les reproductions doivent être aussi courtes que possible tout en montrant exactement le problème rencontré. Les reproductions n’ont pas besoin d’être complexes ou réalistes. Il faut juste qu’elles affichent le code qui est conforme au standard ou à l’implémentation documentée du compilateur, ou dans le cas d’absence de diagnostic, le code qui n’est pas conforme. Les reproductions simples et directes qui contiennent juste assez de code pour illustrer le problème sont les meilleures. Si vous pouvez enlever ou simplifier du code tout en restant conforme et sans modifier le problème, n’hésitez pas. Vous n’avez pas besoin d’ajouter de contre-exemples de code qui fonctionnent. 

- **Est autonome.** Les reproductions doivent éviter les dépendances inutiles. Si vous pouvez reproduire le problème sans bibliothèques tierces, faites-le. Si vous pouvez reproduire le problème sans code de bibliothèque avec des instructions de sortie simples (par exemple, `puts("this shouldn't compile");`, `std::cout << value;` et `printf("%d\n", value);` sont OK), n’hésitez pas. Si l’exemple peut être condensé dans un seul fichier de code source, sans référence à aucun en-tête utilisateur, c’est parfait. Vous nous aiderez considérablement en réduisant la quantité de code que nous devons examiner comme facteur possible du problème.

- **Utilise la dernière version du compilateur.** Les reproductions doivent utiliser la dernière mise à jour vers la dernière version de l’ensemble d’outils ou la préversion la plus récente de la prochaine mise à jour ou de la prochaine version majeure, si possible. Les problèmes que vous pouvez rencontrer dans des versions antérieures de l’ensemble d’outils ont très souvent été résolus dans les versions plus récentes. Les correctifs ne sont reportés que très rarement sur des versions antérieures.

- **Comparée à d’autres compilateurs**, le cas échéant. Les reproductions qui impliquent du code C++ portable doivent vérifier le comportement par rapport à d’autres compilateurs si possible. Le standard finit toujours par déterminer si le programme est correct. Aucun compilateur n’est parfait, mais si Clang et GCC acceptent votre code sans diagnostic alors que MSVC non, vous voyez probablement un bogue dans notre compilateur. (Autres possibilités : des différences de comportement entre Unix et Windows ou différents niveaux d’implémentation de standards C++, etc.) En revanche, si tous les compilateurs rejettent votre code, c’est probablement que votre code est incorrect. Voir différents messages d’erreur peut vous aider à diagnostiquer le problème vous-même.

   Vous pouvez trouver des listes de compilateurs en ligne pour tester votre code avec des [compilateurs C++ en ligne](https://isocpp.org/blog/2013/01/online-c-compilers) sur le site web C++ ISO ou cette [liste de compilateurs C++ en ligne](https://arnemertz.github.io/online-compilers/) organisée sur GitHub. Voici quelques exemples spécifiques : [Wandbox](https://wandbox.org/), [Compiler Explorer](https://godbolt.org/) et [Coliru](http://coliru.stacked-crooked.com/). 

   > [!NOTE]
   > Les sites web de compilateurs en ligne ne sont pas affiliés à Microsoft. De nombreux sites web de compilateurs en ligne sont gérés en tant que projets personnels et certains de ces sites ne seront peut-être pas disponibles lorsque vous lirez ceci, mais vous devriez en trouver d’autres que vous pourrez utiliser.

Les problèmes dans le compilateur, l’éditeur de liens et les bibliothèques ont tendance à apparaître de manière spécifique. Le type de problème que vous rencontrez détermine le type de reproduction à inclure dans votre rapport. Sans une reproduction appropriée, nous n’avons rien à examiner. Voici quelques-uns des types de problèmes que vous pouvez voir et les instructions permettant de générer les types de reproductions que vous devez utiliser pour signaler chaque type de problème.
 
#### <a name="frontend-parser-crash"></a>Blocage de serveur frontal (analyseur)

Les blocages de serveur frontal se produisent pendant la phase d’analyse du compilateur. En règle générale, le compilateur indique [Erreur irrécupérable C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) et fait référence au fichier de code source et au numéro de ligne où l’erreur s’est produite ; il mentionne souvent un fichier msc1.cpp, mais vous pouvez ignorer ce détail.

Pour ce type de blocage, fournissez une [reproduction prétraitée](#preprocessed-repros).

Voici un exemple de sortie du compilateur pour ce type de blocage :

```Output
SandBoxHost.cpp
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        fatal error C1001: An internal error has occurred in the compiler.
(compiler file 'msc1.cpp', line 1369)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        note: This diagnostic occurred in the compiler generated function
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted
        to send an error report to Microsoft later.
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

#### <a name="backend-code-generation-crash"></a>Blocage du backend (génération de code)

Les blocages de serveur principal se produisent pendant la phase de génération de code du compilateur. En règle générale, le compilateur indique [Erreur irrécupérable C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) et peut ne pas référencer le fichier de code source ni le numéro de ligne associés au problème ; il mentionne souvent le compilateur de fichiers\\utc\\src\\p2\\main.c, mais vous pouvez ignorer ce détail.

Pour ce type de blocage, fournissez une [reproduction de lien](#link-repros) si vous utilisez la génération de code durant l’édition de liens (LTCG), activée par l’argument de ligne de commande **/GL** dans cl.exe. Sinon, fournissez une [reproduction prétraitée](#preprocessed-repros) à la place.

Voici un exemple de sortie du compilateur pour un blocage de backend quand la génération LTCG n’est pas utilisée. Si la sortie du compilateur ressemble à ceci, vous devez fournir une [reproduction prétraitée](#preprocessed-repros).

```Output
repro.cpp
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:
        An internal error has occurred in the compiler.
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
INTERNAL COMPILER ERROR in
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

Si la ligne qui commence par **ERREUR INTERNE DU COMPILATEUR** mentionne link.exe plutôt que cl.exe, la génération LTCG a été activée et vous devez fournir une [reproduction de lien](#link-repros). Si le message d’erreur du compilateur n’indique pas clairement si la génération LTCG a été activée, vous devez peut-être examiner les arguments de ligne de commande que vous avez copiés à partir du journal de génération dans une étape précédente pour l’argument de ligne de commande **/GL**.

#### <a name="linker-crash"></a>Blocage d’éditeur de liens

Les blocages d’éditeur de liens se produisent pendant la phase d’édition des liens, après l’exécution du compilateur. En règle générale, l’éditeur de liens indique [Erreur des outils Éditeur de liens LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md).

> [!NOTE]
> Si la sortie mentionne C1001 ou implique la génération de code durant l’édition de liens, reportez-vous plutôt à [Blocage de serveur principal (génération de code)](#backend-code-generation-crash) pour plus d’informations.

Pour ce type de blocage, fournissez une [reproduction de lien](#link-repros).

Voici un exemple de sortie du compilateur pour ce type de blocage.

```Output
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2

  Version 14.00.22816.0

  ExceptionCode            = C0000005
  ExceptionFlags           = 00000000
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)
        "z:\tools\bin\x64\link.exe"
  NumberParameters         = 00000002
  ExceptionInformation[ 0] = 0000000000000000
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF

CONTEXT:

  Rax    = 0000000000000400  R8     = 0000000000000000
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690
  Rdx    = 000000655F97E270  R11    = 0000000000000400
  Rsp    = 000000655F97E248  R12    = 0000000000000000
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000
  Rsi    = 000000655DF82580  R14    = 000000655F97F390
  Rdi    = 0000000000000000  R15    = 0000000000000000
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206
  SegCs  = 0000000000000033  SegDs  = 000000000000002B
  SegSs  = 000000000000002B  SegEs  = 000000000000002B
  SegFs  = 0000000000000053  SegGs  = 000000000000002B
  Dr0    = 0000000000000000  Dr3    = 0000000000000000
  Dr1    = 0000000000000000  Dr6    = 0000000000000000
  Dr2    = 0000000000000000  Dr7    = 0000000000000000
```

Si l’édition des liens incrémentielle est activée et que le blocage se produit seulement après une édition initiale réussie des liens (autrement dit, seulement après la première édition complète des liens sur laquelle l’édition des liens incrémentielle suivante est basée), fournissez également une copie des fichiers objet (.obj) et bibliothèque (.lib) correspondant aux fichiers sources qui ont été modifiés une fois l’édition initiale des liens terminée.

#### <a name="bad-code-generation"></a>Génération de code incorrect

La génération de code incorrect est rare, mais se produit quand le compilateur génère par inadvertance du code incorrect qui entraîne le blocage de votre application au moment de l’exécution au lieu de détecter ce problème au moment de la compilation. Si vous pensez que le problème que vous rencontrez occasionne une génération de code incorrect, traitez votre rapport comme dans [Blocage de serveur principal (génération de code)](#backend-code-generation-crash).

Pour ce type de blocage, fournissez une [reproduction de lien](#link-repros) si vous utilisez la génération de code durant l’édition de liens (LTCG), activée par l’argument de ligne de commande **/GL** dans cl.exe. Sinon, fournissez une [reproduction prétraitée](#preprocessed-repros).

## <a name="how-to-generate-a-repro"></a>Comment générer une reproduction

Pour nous aider à trouver la source du problème, une [bonne reproduction](#what-makes-a-good-repro) est indispensable. Avant de suivre les étapes décrites ci-dessous pour certains types de reproductions, essayez de condenser le code qui illustre le problème autant que possible. Essayez d’éliminer ou de minimiser les dépendances, les en-têtes nécessaires et les bibliothèques, et de limiter les options du compilateur et les définitions de préprocesseur utilisées, si possible.

Vous trouverez ci-dessous des instructions pour générer les différents types de reproductions que vous utiliserez pour signaler différents types de problèmes.

### <a name="preprocessed-repros"></a>Reproductions prétraitées

Une *reproduction prétraitée* est un seul fichier source qui illustre un problème, généré à partir de la sortie du préprocesseur C en utilisant l’option du compilateur **/P** du fichier source de reproduction d’origine. Cela intègre les en-têtes inclus pour supprimer les dépendances sur d’autres fichiers sources et d’en-tête, et résout également des macros, des valeurs #ifdef et d’autres commandes de préprocesseur qui pourraient dépendre de votre environnement local.

> [!NOTE]
> Les reproductions prétraitées ne sont pas aussi utiles pour les problèmes qui peuvent être le résultat de bogues dans notre implémentation de bibliothèque standard, car nous voulons souvent substituer notre dernière implémentation en cours pour voir si nous avons déjà résolu le problème. Dans ce cas, ne prétraitez pas la reproduction et, si vous ne pouvez pas réduire le problème à un seul fichier source, empaquetez votre code dans un fichier .zip ou similaire, ou utilisez une reproduction de projet IDE. Pour plus d’informations, consultez [Autres reproductions](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>Pour prétraiter un fichier de code source

1. Capturez les arguments de ligne de commande utilisés pour générer votre reproduction, comme décrit dans [Pour signaler le contenu de la ligne de commande](#to-report-the-contents-of-the-command-line).

1. Ouvrez l’**invite de commandes développeur** qui correspond à l’architecture de configuration et à la version de Visual Studio utilisées pour générer votre projet.

1. Accédez au répertoire qui contient votre projet de reproduction.

1. Dans la fenêtre de console de l’invite de commandes développeur, entrez la commande **cl /P** *arguments* *filename.cpp*, où *arguments* est la liste des arguments capturés ci-dessus et *filename.cpp* est le nom du fichier source de votre reproduction. Cette commande réplique la ligne de commande utilisée pour la reproduction, mais arrête la compilation après le passage du préprocesseur, et génère en sortie le code source prétraité dans *filename*.i.

Une fois que vous avez généré le fichier prétraité, il est judicieux de vérifier que le problème se reproduit toujours avec le fichier prétraité.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Pour confirmer que l’erreur se reproduit toujours avec le fichier prétraité

1. Dans la fenêtre de console de l’invite de commandes développeur, entrez la commande **cl** *arguments* **/TP** *filename***.i** pour indiquer à cl.exe de compiler le fichier prétraité en fichier source C++, où *arguments* est la liste des arguments capturés ci-dessus, mais avec les arguments **/D** et **/I** supprimés (car ils ont déjà été inclus dans le fichier prétraité) ; et où *filename***.i** est le nom de votre fichier prétraité.

1. Confirmez que le problème est reproduit.

Enfin, attachez la reproduction prétraitée *filename*.i à votre rapport.

### <a name="link-repros"></a>Reproductions de liens

Une *reproduction de lien* est le contenu généré par l’éditeur de liens d’un répertoire spécifié par la variable d’environnement **link\_repro**. Elle contient les artefacts de build qui montrent collectivement un problème qui se produit au moment de la liaison, par exemple un blocage de backend qui implique la génération de code d’édition de liens (LTCG), ou un blocage de l’éditeur de liens. Ces artefacts de build sont ceux nécessaires comme entrée de l’éditeur de liens pour que le problème puisse être reproduit. Une reproduction de lien peut être créée facilement à l’aide de cette variable d’environnement pour activer la fonctionnalité de génération de reproduction intégrée de l’éditeur de liens.

#### <a name="to-generate-a-link-repro"></a>Pour générer une reproduction de lien

1. Capturez les arguments de ligne de commande utilisés pour générer votre reproduction, comme décrit dans [Pour signaler le contenu de la ligne de commande](#to-report-the-contents-of-the-command-line).

1. Ouvrez l’**invite de commandes développeur** qui correspond à l’architecture de configuration et à la version de Visual Studio utilisées pour générer votre projet.

1. Dans la fenêtre de console de l’invite de commandes développeur, accédez au répertoire qui contient votre projet de reproduction.

1. Entrez **mkdir linkrepro** pour créer un répertoire dédié à la reproduction de lien.

1. Entrez la commande **set link\_repro=linkrepro** pour définir la variable d’environnement **link\_repro** sur le répertoire que vous venez de créer.

1. Pour générer le projet de reproduction dans Visual Studio, dans la fenêtre de la console de l’invite de commandes développeur, entrez la commande **devenv**. Cela garantit que la valeur de la variable d’environnement **link\_repro** est visible dans Visual Studio. Pour générer le projet sur la ligne de commande, utilisez les arguments de ligne de commande capturés au-dessus pour dupliquer la build de reproduction.

1. Générez votre projet de reproduction et confirmez que le problème attendu s’est produit.

1. Fermez Visual Studio si vous l’avez utilisé pour effectuer la build.

1. Dans la fenêtre de la console de l’invite de commandes développeur, entrez la commande **set link\_repro=** pour effacer la variable d’environnement **link\_repro**.

Enfin, empaquetez la reproduction en compressant l’ensemble du répertoire linkrepro dans un fichier .zip ou similaire et attachez-la à votre rapport.

### <a name="other-repros"></a>Autres reproductions

Si vous ne pouvez pas réduire le problème à un seul fichier source ou une reproduction prétraitée et que le problème ne nécessite pas une reproduction de lien, nous pouvons examiner un projet IDE. Toutes les instructions sur la création d’une bonne reproduction s’appliquent aussi : le code doit être minime et autonome, le problème doit se produire dans nos outils plus récent, et le cas échéant, le problème ne doit pas apparaître dans d’autres compilateurs.

Créez votre reproduction comme un projet IDE minimal, puis empaquetez-la en compressant l’intégralité de la structure de répertoire dans un fichier .zip ou similaire et attachez-la à votre rapport.

## <a name="ways-to-send-your-report"></a>Modes d’envoi de votre rapport

Vous disposez de plusieurs moyens pour nous faire parvenir votre rapport. Vous pouvez utiliser les pages intégrées de Visual Studio [Outil Signaler un problème](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) ou [Communauté de développeurs Visual Studio](https://developercommunity.visualstudio.com/). Il est également possible d’envoyer un e-mail avec votre rapport, mais les deux premières méthodes sont préférables. Le choix dépend de la façon dont vous voulez communiquer avec les ingénieurs qui vont étudier votre rapport, et si vous voulez suivre sa progression ou le partager avec la communauté.

> [!NOTE]
> Quelle que soit la manière dont vous envoyez votre rapport, Microsoft respecte votre vie privée. Pour plus d’informations sur la façon dont nous utilisons les données que vous nous envoyez, consultez [Déclaration de confidentialité des produits Microsoft Visual Studio](https://www.visualstudio.com/dn948229).

### <a name="use-the-report-a-problem-tool"></a>Utiliser l’outil Signaler un problème

L’outil **Signaler un problème** dans Visual Studio est un moyen pour les utilisateurs de Visual Studio de signaler différents problèmes en quelques clics. Il fournit un formulaire simple qui vous permet de spécifier des informations détaillées sur le problème que vous avez rencontré et d’envoyer ensuite votre rapport sans jamais quitter l’IDE.

L’outil **Signaler un problème** est facile et pratique à utiliser à partir de l’IDE. Vous pouvez y accéder à partir de la barre de titre en choisissant l’icône **Envoyer des commentaires** à côté de la zone de recherche **Lancement rapide**, ou vous pouvez le trouver sur la barre de menus dans **Aide** >  **Envoyer des commentaires** > **Signaler un problème**.

Quand vous choisissez de signaler un problème, cherchez d’abord s’il en existe de similaires dans la Communauté des développeurs. Si votre problème a déjà été signalé, votez pour la rubrique et ajoutez des commentaires qui ajoutent de nouveaux éléments. Si vous ne voyez pas de problème similaire, choisissez le bouton **Signaler un nouveau problème** dans le bas de la boîte de dialogue Commentaires sur Visual Studio et suivez les étapes pour signaler votre problème.

### <a name="use-the-visual-studio-developer-community-pages"></a>Utiliser les pages de la Communauté des développeurs Visual Studio

Les pages de la Communauté des développeurs Visual Studio sont un autre moyen pratique de signaler des problèmes et trouver des solutions pour Visual Studio, le compilateur C++, les outils et les bibliothèques. La page [Visual Studio Questions](https://developercommunity.visualstudio.com/spaces/8/index.html) est l’endroit où vous pouvez signaler des problèmes avec l’IDE ou l’installation. Pour les problèmes relatifs au compilateur, à l’éditeur de liens, et aux autres outils et bibliothèques C++, utilisez la page [C++ Questions](https://developercommunity.visualstudio.com/spaces/62/index.html).

Dans la bannière Communauté de développeurs située en haut de chaque page se trouve une zone de recherche, que vous pouvez utiliser pour rechercher des publications ou des rubriques qui signalent des problèmes similaires aux vôtres. Il est possible qu’une solution ou d’autres informations utiles relatives à votre problème soient déjà disponibles dans une rubrique existante. Si quelqu’un a signalé le même problème, votez pour cette rubrique et ajoutez-y des commentaires au lieu de signaler un nouveau problème.

Si votre problème n’a pas déjà été signalé, choisissez le bouton **Signaler un problème** en regard de la zone de recherche de la page Communauté des développeurs. Vous pouvez être invité à vous connecter à votre compte Visual Studio et à accepter de donner à l’application Communauté des développeurs un accès à votre profil. Une fois connecté, vous accédez directement à une page où vous pouvez signaler le problème. Vous pouvez inclure le code et la ligne de commande de votre reproduction, des captures d’écran, des liens vers des discussions qui s’y rapportent, et toute autre information que vous pensez pertinente et utile.

### <a name="send-an-email"></a>Envoyer un e-mail

Un e-mail constitue un autre moyen d’envoyer votre rapport directement à l’équipe Visual C++. Vous pouvez nous contacter à l’adresse [compilercrash@microsoft.com](mailto:compilercrash@microsoft.com). Utilisez cette méthode seulement si les deux autres ne sont pas disponibles, car les e-mails ne sont pas suivis d’aussi près que les problèmes signalés à la Communauté des développeurs via l’outil **Signaler un problème** ou via les pages web, et les commentaires et les solutions ne sont pas visibles par d’autres utilisateurs de Visual Studio.

Si vous choisissez d’envoyer votre rapport par e-mail, vous pouvez utiliser le modèle suivant comme corps de votre message. N’oubliez pas de joindre le code source ou d’autres fichiers si vous n’indiquez pas ces informations dans le corps du message.

```Example
To: compilercrash@microsoft.com
Subject: Visual C++ Error Report
-----

Compiler version:

CL.EXE command line:

Problem description:

Source code and repro steps:

```

> [!TIP]
> Pour d’autres types de problèmes que vous pouvez rencontrer dans Visual Studio et qui ne sont pas liés à l’ensemble d’outils (par exemple, des problèmes d’interface utilisateur, des fonctionnalités IDE altérées ou des blocages d’ordre général), l’outil Signaler un problème peut s’avérer être un choix particulièrement judicieux en raison de ses fonctionnalités de capture d’écran et de sa capacité à enregistrer les actions de l’interface utilisateur qui aboutissent au problème que vous avez rencontré. Vous ne devez jamais signaler ces autres types d’erreurs en envoyant un e-mail à compilercrash@microsoft.com.
