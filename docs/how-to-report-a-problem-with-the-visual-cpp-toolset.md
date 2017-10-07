---
title: "Guide pratique pour signaler un problème avec l’ensemble d’outils Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: ec24a49c-411d-47ce-aa4b-8398b6d3e8f6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2ea129ac94cb1ddc7486ba69280dc0390896e088
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset"></a>Guide pratique pour signaler un problème avec l’ensemble d’outils Visual C++
Si vous rencontrez des problèmes avec le compilateur Visual C++, l’éditeur de liens ou d’autres outils, nous aimerions le savoir.  
  
 La meilleure façon de nous informer d’un problème consiste à nous envoyer un rapport qui inclut une description du problème que vous avez rencontré, des informations sur la façon dont vous créez votre programme et le code qui nous servira à reproduire le problème sur nos propres ordinateurs. Ces informations nous permettent de vérifier rapidement que le problème existe et qu’il n’est pas propre à votre environnement, de déterminer s’il affecte d’autres versions du compilateur et de diagnostiquer sa cause.  
  
 Dans ce document, vous obtiendrez plus d’informations sur les procédures suivantes  
  
-   [Comment préparer votre rapport](#prepare) et les éléments essentiels à un bon rapport.  
  
-   [Modes d’envoi de votre rapport](#send) et leurs différences.  
  
-   [Comment générer une reproduction](#generate) et les différents types de reproductions.  
  
 Vos rapports sont importants pour nous ainsi que pour d’autres développeurs comme vous. Merci de nous aider à améliorer Visual C++ !  
  
##  <a name="prepare"></a> Comment préparer votre rapport  
 Il est important de créer un rapport de qualité, car il est très difficile de reproduire le problème rencontré sur nos propres ordinateurs sans des informations complètes. Plus votre rapport est exhaustif, plus nous serons en mesure de recréer et diagnostiquer le problème efficacement.  
  
 Au minimum, votre rapport doit contenir les éléments suivants :  
  
-   Informations sur la version complète de l’ensemble d’outils que vous utilisez.  
  
-   Ligne de commande cl.exe complète utilisée pour générer votre code.  
  
-   Description détaillée du problème rencontré.  
  
-   « Reproduction », code source qui illustre le problème.  
  
 Poursuivez votre lecture pour en savoir plus sur les informations spécifiques dont nous avons besoin et l’endroit où vous pouvez les trouver.  
  
### <a name="the-toolset-version"></a>Version de l’ensemble d’outils  
 Nous avons besoin des informations sur la version complète de l’ensemble d’outils que vous utilisez pour pouvoir tester votre reproduction avec le même ensemble d’outils sur nos ordinateurs. Si nous pouvons reproduire le problème, ces informations nous donnent également un point de départ pour rechercher si d’autres versions de l’ensemble d’outils présentent le même problème.  
  
##### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>Pour indiquer la version complète du compilateur que vous utilisez  
  
1.  Appuyez sur la touche Windows de votre clavier et commencez à taper `Developer Command Prompt`.  
  
2.  Choisissez la version **Invite de commandes développeur** qui correspond à la version de Visual Studio que vous utilisez quand elle apparaît dans la liste des correspondances.  
  
3.  Dans la console **Invite de commandes développeur**, entrez la commande `cl /Bv /CLR`.  
  
 La sortie doit ressembler à ceci :  
  
```  
C:\Compiler>cl /Bv /CLR  
Microsoft (R) C/C++ Optimizing Compiler Version 18.00.40209  
for Microsoft (R) .NET Framework version 4.00.30319.34014  
Copyright (C) Microsoft Corporation.  All rights reserved.  
  
Compiler Passes:  
 C:\WinCComp\binaries.x86chk\bin\i386\cl.exe:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1xx.dll:      Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c2.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\link.exe:      Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\mspdb120.dll:  Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\1033\clui.dll: Version 18.00.40209.0  
 Common Language Runtime:                            Version  4.00.30319.34014  
  
cl : Command line error D8003 : missing source filename   
```  
  
 Copiez et collez l’intégralité de la sortie dans votre rapport.  
  
### <a name="the-command-line"></a>Ligne de commande  
 Nous avons besoin de la ligne de commande complète (cl.exe et ses arguments) utilisée pour générer votre code afin de pouvoir le générer exactement de la même façon sur nos ordinateurs. Ce point est important, car le problème que vous avez rencontré peut uniquement se produire lors de la génération avec un certain argument ou une certaine combinaison d’arguments.  
  
 L’endroit le plus approprié pour trouver ces informations se situe dans le journal de génération immédiatement après avoir rencontré le problème. Cela permet de garantir que la ligne de commande contient exactement les mêmes arguments pouvant contribuer au problème.  
  
##### <a name="to-report-the-contents-of-the-command-line"></a>Pour signaler le contenu de la ligne de commande  
  
1.  Recherchez le fichier **CL.command.1.tlog** et ouvrez-le. Par défaut, ce fichier se trouve dans \\...\Visual Studio Version\Projects\SolutionName\ProjectName\Config\ProjectName.tlog\CL.command.1.tlog.  
  
     Dans ce fichier, vous trouverez les noms des fichiers de code source suivis des arguments de ligne de commande utilisés pour les compiler, chacun sur une ligne distincte.  
  
2.  Recherchez la ligne qui contient le nom du fichier de code source dans lequel le problème se produit ; la ligne en dessous contient la commande cl.exe correspondante et ses arguments.  
  
 Copiez et collez l’intégralité de la ligne de commande dans votre rapport.  
  
### <a name="a-description-of-the-problem"></a>Description du problème  
 Nous avons besoin d’une description détaillée du problème que vous avez rencontré pour pouvoir vérifier que nous constatons le même effet sur nos ordinateurs ; il nous est également parfois utile de savoir ce que vous tentiez d’effectuer et ce à quoi vous vous attendiez.  
  
 Indiquez les messages d’erreur précis affichés par l’ensemble d’outils, une brève description de ce que vous tentiez d’effectuer pour nous aider à comprendre le code de reproduction ainsi que tous les autres détails qui peuvent nous aider à diagnostiquer le problème rencontré, comme les solutions de contournement que vous avez peut-être trouvées. Évitez de répéter des informations qui figurent ailleurs dans votre rapport.  
  
### <a name="the-repro"></a>Reproduction  
 Nous avons besoin d’une reproduction, un exemple de code source autonome qui illustre le problème que vous avez rencontré, pour pouvoir reproduire l’erreur sur nos ordinateurs. Le type de problème que vous rencontrez détermine le type de reproduction à inclure dans votre rapport. Sans une reproduction appropriée, nous n’avons rien à examiner.  
  
 Des reproductions courtes et autonomes peuvent être incluses directement dans le texte de votre rapport, mais de plus grandes reproductions de code source doivent être jointes au rapport. Les reproductions qui ne peuvent pas être réduites à un fichier de code source unique doivent être empaquetées par la compression d’un répertoire contenant tous les fichiers dans un fichier .zip ou similaire et attachées au rapport. Tous les détails supplémentaires spécifiques au scénario doivent toujours être inclus dans le texte du rapport, jamais dans le code source.  
  
 Le meilleur type de reproduction que vous pouvez nous faire parvenir est une *reproduction minimale*. Il s’agit d’un fichier de code source unique et autonome (sans références aux en-têtes d’utilisateurs) qui contient juste suffisamment de code pour illustrer le problème. Si vous pouvez fournir une reproduction sous cette forme, joignez simplement le fichier de code source à votre rapport ; cela nous suffit.  
  
 Si vous ne pouvez pas réduire le problème à une reproduction minimale sans dépendances, reportez-vous aux sections suivantes pour déterminer le type de reproduction à inclure dans votre rapport.  
  
#### <a name="frontend-parser-crash"></a>Blocage de serveur frontal (analyseur)  
 Les blocages de serveur frontal se produisent pendant la phase d’analyse du compilateur. En règle générale, le compilateur indique [Erreur irrécupérable C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) et fait référence au fichier de code source et au numéro de ligne où l’erreur s’est produite ; il mentionne souvent un fichier msc1.cpp, mais vous pouvez ignorer ce détail.  
  
 Pour ce type de blocage, fournissez une [reproduction prétraitée](#preprocessed_repro).  
  
 Voici un exemple de sortie du compilateur pour ce type de blocage :  
  
```  
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
  
####  <a name="backend_crash"></a> Blocage de serveur principal (génération de code)  
 Les blocages de serveur principal se produisent pendant la phase de génération de code du compilateur. En règle générale, le compilateur indique [Erreur irrécupérable C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) et peut ne pas faire référence au fichier de code source ni au numéro de ligne associés au problème ; il mentionne souvent un fichier compiler\utc\src\p2\main.c, mais vous pouvez ignorer ce détail.  
  
 Pour ce type de blocage, fournissez une [reproduction de lien](#link_repro) si vous utilisez la génération de code durant l’édition de liens (LTCG) ou une [reproduction prétraitée](#preprocessed_repro) dans le cas contraire. La génération LTCG est activée par l’argument de ligne de commande `/GL` sur cl.exe.  
  
 Voici un exemple de sortie du compilateur pour ce type de blocage quand la génération LTCG n’est **pas** utilisée. Si la sortie du compilateur ressemble à ceci, vous devez fournir une [reproduction prétraitée](#preprocessed_repro).  
  
```  
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
  
 Si la ligne qui commence par **ERREUR INTERNE DU COMPILATEUR** mentionne link.exe plutôt que cl.exe, la génération LTCG a été activée et vous devez fournir une [reproduction de lien](#link_repro). Si le message d’erreur du compilateur n’indique pas clairement si la génération LTCG a été activée, vous devez peut-être examiner les arguments de ligne de commande que vous avez copiés à partir du journal de génération dans une étape précédente pour l’argument de ligne de commande `/GL`.  
  
#### <a name="linker-crash"></a>Blocage d’éditeur de liens  
 Les blocages d’éditeur de liens se produisent pendant la phase d’édition des liens, après l’exécution du compilateur. En règle générale, l’éditeur de liens indique [Erreur des outils Éditeur de liens LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md).  
  
> [!NOTE]
>  Si la sortie mentionne C1001 ou implique la génération de code durant l’édition de liens, reportez-vous plutôt à [Blocage de serveur principal (génération de code)](#backend_crash) pour plus d’informations.  
  
 Pour ce type de blocage, fournissez une [reproduction de lien](#link_repro).  
  
 Voici un exemple de sortie du compilateur pour ce type de blocage.  
  
```  
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
  
 Si l’édition des liens incrémentielle est activée et que le blocage se produit uniquement après l’édition des liens initiale, autrement dit uniquement après la première édition des liens complète sur laquelle repose l’édition des liens incrémentielle à venir, fournissez également une copie des fichiers objet (.obj) et bibliothèque (.lib) qui correspondent aux fichiers sources qui ont été modifiés à la fin de l’édition des liens initiale.  
  
#### <a name="bad-code-generation"></a>Génération de code incorrect  
 La génération de code incorrect est rare, mais se produit quand le compilateur génère par inadvertance du code incorrect qui entraîne le blocage de votre application au moment de l’exécution au lieu de détecter ce problème au moment de la compilation. Si vous pensez que le problème que vous rencontrez occasionne une génération de code incorrect, traitez votre rapport comme dans [Blocage de serveur principal (génération de code)](#backend_crash).  
  
 Pour ce type de blocage, fournissez une [reproduction de lien](#link_repro) si vous utilisez la génération de code durant l’édition de liens (LTCG) ou une [reproduction prétraitée](#preprocessed_repro) dans le cas contraire. La génération LTCG est activée par l’argument de ligne de commande `/GL` sur cl.exe.  
  
##  <a name="send"></a> Modes d’envoi de votre rapport  
 Vous disposez de plusieurs moyens pour nous faire parvenir votre rapport. Vous pouvez signaler un bogue sur Microsoft Connect, nous envoyer un e-mail ou utiliser l’outil Signaler un problème intégré à Visual Studio. Le meilleur choix pour votre rapport dépend du type de problème que vous avez rencontré, comment vous souhaitez interagir avec les ingénieurs qui vont étudier votre rapport et si vous souhaitez suivre sa progression ou le partager avec la communauté.  
  
> [!NOTE]
>  Quelle que soit la manière dont vous envoyez votre rapport, Microsoft respecte votre vie privée. Pour plus d’informations sur la façon dont nous utilisons les données que vous nous envoyez, consultez [Déclaration de confidentialité des produits Microsoft Visual Studio](https://www.visualstudio.com/dn948229).  
  
### <a name="file-a-bug-on-microsoft-connect"></a>Signaler un bogue sur Microsoft Connect  
 Microsoft Connect ([connect.microsoft.com](http://connect.microsoft.com)) permet à notre communauté d’utilisateurs de se connecter directement aux équipes qui développent des produits Microsoft. Sur Connect, vous pouvez signaler de nouveaux bogues et effectuer des demandes de fonctionnalités, afficher d’autres bogues et demandes provenant de la communauté et indiquer ceux qui sont le plus importants pour vous.  
  
 Le signalement de votre problème via Connect est plus approprié quand vous souhaitez partager votre rapport avec la communauté Visual Studio et suivre sa progression publiquement ; en partageant votre rapport, d’autres utilisateurs peuvent parfois fournir des solutions de contournement ou des informations supplémentaires qui peuvent nous aider à diagnostiquer le problème. Vous pouvez toujours utiliser Connect si vous souhaitez préserver la confidentialité de votre rapport (comme quand vous ne pouvez pas partager le code dans votre rapport), mais veillez à définir la visibilité privée de votre rapport avant d’envoyer le formulaire.  
  
-   [Microsoft Connect : Signaler un problème avec Visual Studio 2015 Update 3](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6493)  
  
-   [Microsoft Connect : Signaler un problème avec Visual Studio 2015 Update 2](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6406)  
  
-   [Microsoft Connect : Signaler un problème avec Visual Studio 2015 Update 1](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6326)  
  
-   [Microsoft Connect : Signaler un problème avec Visual Studio 2015](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6240)  
  
 Vous pouvez signaler un problème avec d’autres produits Visual Studio et .Net Framework en recherchant le produit dans la liste déroulante de la page Connect [Commentaires sur Visual Studio et .NET Framework](https://connect.microsoft.com/VisualStudio/feedback/LoadSubmitFeedbackForm).  
  
### <a name="send-an-email"></a>Envoyer un e-mail  
 L’e-mail représente un autre moyen d’envoyer votre rapport directement à l’équipe Visual C++ ; vous pouvez nous contacter à l’adresse [compilercrash@microsoft.com](mailto:compilercrash@microsoft.com).  
  
 En signalant votre problème par e-mail, vous ne bénéficiez pas de l’aide de la riche communauté Microsoft Connect, mais cette option peut être plus appropriée pour les reproductions de grande taille. Cela peut également être la meilleure ou la seule option si votre environnement de travail n’est pas connecté à Internet ou que vous ne pouvez pas utiliser Microsoft Connect pour toute autre raison.  
  
 Si vous choisissez d’envoyer votre rapport par e-mail, vous pouvez utiliser le modèle suivant comme corps de votre message. N’oubliez pas de joindre le code source ou d’autres fichiers si vous n’indiquez pas ces informations dans le corps du message.  
  
```  
To: compilercrash@microsoft.com  
Subject: Visual C++ Error Report  
-----  
  
Compiler version:  
  
CL.EXE command line:  
  
Problem description:  
  
Source code and repro steps:  
  
```  
  
### <a name="use-the-report-a-problem-tool"></a>Utiliser l’outil Signaler un problème  
 L’outil Signaler un problème dans Visual Studio est un moyen pour les utilisateurs de Visual Studio de signaler divers problèmes en quelques clics. Il fournit un formulaire simple qui vous permet de spécifier des informations détaillées sur le problème que vous avez rencontré et d’envoyer ensuite votre rapport sans jamais quitter l’IDE.  
  
 Le signalement de votre problème via l’outil Signaler un problème n’est pas courant pour les types de problèmes d’ensembles d’outils présentés dans ce document ; néanmoins, il s’agit d’une option que vous pouvez choisir si elle vous convient.  
  
> [!TIP]
>  Pour d’autres types de problèmes que vous pouvez rencontrer dans Visual Studio et qui ne sont pas liés à l’ensemble d’outils (par exemple, des problèmes d’interface utilisateur, des fonctionnalités IDE altérées ou des blocages d’ordre général), l’outil Signaler un problème peut s’avérer être un choix particulièrement judicieux en raison de ses fonctionnalités de capture d’écran et de sa capacité à enregistrer les actions de l’interface utilisateur qui aboutissent au problème que vous avez rencontré. Microsoft Connect peut également représenter une option pertinente pour le signalement de ces autres types d’erreurs, mais ne présente pas les fonctionnalités supplémentaires de l’outil Signaler un problème. Vous ne devez jamais signaler ces autres types d’erreurs en envoyant un e-mail à compilercrash@microsoft.com.  
  
##  <a name="generate"></a> Génération de reproductions  
 Une reproduction est un exemple de code complet et autonome qui illustre le problème que vous signalez. Une reproduction n’est **pas** un extrait de code, mais doit être un exemple complet capable de générer et de s’exécuter (ou qui devrait, sans les erreurs produites par le problème que vous signalez). Elle doit contenir toutes les directives #include nécessaires, même pour les en-têtes standard.  
  
 En outre, une bonne reproduction  
  
-   **Est minimale.** Les reproductions doivent être aussi réduites que possible tout en illustrant toujours avec précision le problème rencontré. Elles ne doivent pas être complexes ni réalistes, mais de préférence simples et pertinentes. Il n’est pas obligatoire d’y inclure des contre-exemples de code qui fonctionne, mais cela est possible à titre d’illustration ; seul l’exemple de code à l’origine du problème est nécessaire.  
  
-   **Est autonome.** Les reproductions doivent éviter les dépendances inutiles. Si vous pouvez reproduire le problème sans bibliothèques tierces, faites-le. Si vous pouvez reproduire le problème sans aucun code de bibliothèque (`std::out`, `printf()` sont acceptés), faites-le. Vous nous aiderez considérablement en réduisant la quantité de code que nous devons examiner comme facteur possible du problème.  
  
-   **Utilise la dernière version du compilateur.** Les reproductions doivent utiliser la dernière version de l’ensemble d’outils dès que possible. Des problèmes que vous pouvez toujours rencontrer dans des versions antérieures de l’ensemble d’outils ont très souvent été résolus dans les versions plus récentes.  
  
-   **Est comparée à d’autres compilateurs**, le cas échéant. Les reproductions qui impliquent du code C++ portable doivent vérifier le comportement par rapport à d’autres compilateurs si possible.  
  
     Cette étape permet de déterminer si votre code est correct, comme quand MSVC est en désaccord avec Clang et GCC, ou incorrect, comme quand MSVC, Clang et GCC conviennent que votre code génère l’erreur.  
  
 Vous trouverez ci-dessous des instructions pour générer les différents types de reproductions que vous utiliserez pour signaler différents types de problèmes.  
  
###  <a name="preprocessed_repro"></a> Reproductions prétraitées  
 Une reproduction prétraitée est un fichier source unique qui illustre un problème et a été généré à partir de la sortie du préprocesseur C par le traitement du fichier source d’origine. Ce processus intègre les en-têtes Include pour supprimer les dépendances sur d’autres fichiers sources et d’en-tête, et résout également des macros, des valeurs #ifdef et d’autres commandes de préprocesseur qui pourraient dépendre de votre environnement local.  
  
> [!NOTE]
>  Notez que les reproductions prétraitées sont moins pratiques pour les problèmes qui peuvent être le résultat de bogues dans notre implémentation de bibliothèque standard, car il est souvent utile de substituer notre dernière implémentation en cours pour voir si nous avons déjà résolu le problème. Dans ce cas, ne prétraitez pas la reproduction et, si vous ne pouvez pas réduire le problème à un fichier source unique, empaquetez votre code dans un fichier .zip ou similaire, ou envisagez d’utiliser une reproduction de projet IDE (consultez [Autres reproductions](#other_repros) ci-dessous).  
  
##### <a name="to-preprocess-a-source-code-file"></a>Pour prétraiter un fichier de code source  
  
1.  Appuyez sur la touche Windows de votre clavier et commencez à taper `Developer Command Prompt`.  
  
2.  Choisissez la version **Invite de commandes développeur** qui correspond à la version de Visual Studio que vous utilisez quand elle apparaît dans la liste des correspondances.  
  
3.  Dans la fenêtre de console **Invite de commandes développeur**, entrez la commande `cl /P argumentsfilename.cpp`.  
  
 Une fois que vous disposez du fichier prétraité (désormais filename.i), il est judicieux de vérifier que le problème se reproduit toujours avec le fichier prétraité. Vous pouvez utiliser l’argument de ligne de commande `/TP` pour indiquer à cl.exe d’ignorer l’étape de préprocesseur et de tenter de compiler comme d’habitude.  
  
##### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Pour confirmer que l’erreur se reproduit toujours avec le fichier prétraité  
  
1.  Appuyez sur la touche Windows de votre clavier et commencez à taper `Developer Command Prompt`.  
  
2.  Choisissez la version **Invite de commandes développeur** qui correspond à la version de Visual Studio que vous utilisez quand elle apparaît dans la liste des correspondances.  
  
3.  Dans la fenêtre de console **Invite de commandes développeur**, entrez la commande `cl arguments /TP filename.i`.  
  
4.  Confirmez que le problème est reproduit.  
  
 Enfin, joignez cette reproduction à votre rapport.  
  
###  <a name="link_repro"></a> Reproductions de lien  
 Une reproduction de lien est un répertoire unique contenant des artefacts de build qui illustrent collectivement un problème qui se produit durant l’édition de liens, par exemple un blocage de serveur principal impliquant la génération de code durant l’édition de liens (LTCG) ou un blocage d’éditeur de liens ; les artefacts de build inclus sont ceux qui sont nécessaires comme entrée de l’éditeur de liens pour que le problème puisse être reproduit. Les reproductions de lien peuvent être créées facilement en utilisant les fonctionnalités fournies par l’éditeur de liens.  
  
##### <a name="to-generate-a-link-repro"></a>Pour générer une reproduction de lien :  
  
1.  Ouvrez une invite de commandes et entrez la commande `mkdir directory` pour créer un répertoire pour la reproduction de lien.  
  
2.  Définissez la variable d’environnement link_repro sur le répertoire que vous venez de créer et entrez la commande `set link_repro=directory`.  
  
3.  Si vous souhaitez effectuer la génération à partir de Visual Studio, lancez-le à partir de l’invite de commandes en entrant la commande `devenv`. Cela garantit que la valeur de la variable d’environnement link_repro est visible dans Visual Studio.  
  
4.  Générez votre application et confirmez que le problème attendu s’est produit.  
  
5.  Fermez Visual Studio maintenant si vous l’avez lancé à l’étape 3.  
  
6.  Effacez la variable d’environnement link_repro et entrez la commande `set link_repro=`  
  
 Enfin, empaquetez la reproduction en compressant l’ensemble du répertoire dans un fichier .zip ou similaire et attachez-la à votre rapport.  
  
###  <a name="other_repros"></a> Autres reproductions  
 Si vous ne pouvez pas réduire le problème à un fichier source unique ou une reproduction prétraitée et que le problème ne nécessite pas une reproduction de lien, nous pouvons examiner un projet IDE. Le code dans le projet doit toujours être minimal et tous les conseils de ce document s’appliquent encore.  
  
 Créez votre reproduction comme un projet IDE minimal, puis empaquetez-la en compressant l’intégralité de la structure de répertoire dans un fichier .zip ou similaire et attachez-la à votre rapport.
