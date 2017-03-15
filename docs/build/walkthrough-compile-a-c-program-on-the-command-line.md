---
title: "Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C sur la ligne de commande | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
helpviewer_keywords: 
  - "compilation d'un programme C (C++)"
  - "applications en ligne de commande (C++), programmes C"
  - "compiler des programmes (C++)"
  - "Visual C, compiler"
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
caps.latest.revision: 46
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C sur la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] inclut un compilateur C que vous pouvez utiliser pour créer toutes sortes de programmes, des programmes de console de base aux applications de bureau Windows.  
  
 Cette procédure pas à pas explique comment créer un programme C de base à l'aide d'un éditeur de texte, puis le compiler depuis la ligne de commande.  
  
 Vous pouvez utiliser vos propres programmes C au lieu de taper les exemples de programmes donnés dans cette procédure.  Vous pouvez également utiliser tous les exemples de programmes C des rubriques d'aide.  
  
 Par défaut, le compilateur Visual C\+\+ traite tous les fichiers se terminant par .c comme code source C et tous les fichiers se terminant par .cpp comme code source C\+\+.  Pour forcer le compilateur à traiter tous les fichiers en tant que fichiers de code C, indépendamment de leur extension, utilisez l'option du compilateur [\/Tc](../build/reference/tc-tp-tc-tp-specify-source-file-type.md).  
  
## Composants requis  
 Vous devez posséder des notions de base du langage C.  
  
### Pour créer un fichier source C et le compiler depuis la ligne de commande  
  
1.  Ouvrez une invite de commandes développeur.  Dans Windows 8, dans l'**écran d'accueil**, ouvrez le dossier **Visual Studio Tools**, puis choisissez le raccourci **Invite de commandes développeur**.  Dans les versions antérieures de Windows, sélectionnez le bouton **Démarrer**, développez **Tous les programmes**, **Microsoft Visual Studio**, **Visual Studio Tools**, puis choisissez **Invite de commandes développeur**.  
  
     Selon la version de Windows installée sur l'ordinateur et la configuration de sécurité du système, vous devrez peut\-être ouvrir le menu contextuel pour **Invite de commandes développeur**, puis sélectionner **Exécuter en tant qu'administrateur** pour générer et exécuter avec succès l'application que vous créez à l'aide de cette procédure.  
  
    > [!NOTE]
    >  L'**Invite de commandes développeur** définit automatiquement le chemin d'accès correct du compilateur C et de toutes les bibliothèques requises.  Utilisez\-le à la place de la fenêtre habituelle d'invite de commandes.  Pour plus d'informations, consultez [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
2.  À l'invite de commandes, créez un répertoire pour votre fichier source et faites\-en le répertoire de travail actif.  Par exemple, tapez **md c:\\simple** et appuyez sur Entrée pour créer un répertoire nommé « simple », puis tapez **cd c:\\simple** et appuyez sur Entrée pour accéder à ce répertoire.  
  
3.  À l'invite de commandes, tapez **notepad** puis appuyez sur Entrée.  
  
4.  Dans le Bloc\-notes, tapez les lignes suivantes.  
  
     [!code-cpp[NVC_Walkthrough_Compile_C#100](../build/codesnippet/CPP/walkthrough-compile-a-c-program-on-the-command-line_1.c)]  
  
5.  Dans la barre de menus, sélectionnez **Fichier**, puis **Enregistrer** pour ouvrir la boîte de dialogue **Enregistrer sous**.  Accédez au répertoire que vous avez créé.  Dans la zone **Nom de fichier**, entrez un nom pour votre source fichier \(par exemple simple.c\) puis, dans la liste déroulante **Type de fichier**, sélectionnez **Tous les fichiers \(\*.\*\)**.  Sélectionnez le bouton **Enregistrer** pour créer un fichier source C dans votre répertoire de travail.  
  
6.  À l'invite de commandes, tapez **dir**, puis appuyez sur Entrée.  Vous devez voir le fichier source que vous avez créé :  
  
  **C:\\simple\>dir**  
 **Le volume dans le lecteur C n'a pas de nom.  Le numéro de série du volume est CC62\-6545**  
 **Répertoire de C:\\simple**  
**10\/02\/2012  15:46    \<REP\>          .  10\/02\/2012  15:46    \<REP\>          ..  10\/02\/2012  15:36               102 simple.c**  
 **1 Fichier\(s\)            102 octets**  
 **2 Rép\(s\) 514 900 566 016 octets libres**      Les détails seront différents sur votre ordinateur.  Si vous ne voyez pas votre fichier de code source, assurez\-vous d'avoir accédé au répertoire que vous avez créé et que vous y enregistrez bien votre fichier source avec une extension de nom de fichier .c.  
  
7.  À l'invite de commandes, spécifiez la commande **cl** avec le nom de votre source fichier, par exemple **cl simple.c**, puis appuyez sur Entrée pour compiler le programme.  Le compilateur cl.exe génère un fichier .obj contenant le code compilé, puis exécute l'éditeur de liens pour générer un programme exécutable qui porte le nom de votre fichier source, mais dont l'extension de nom de fichier est .exe, par exemple simple.exe.  
  
     Vous pouvez voir le nom du programme exécutable dans les lignes d'informations de sortie affichées par le compilateur.  
  
     **Sortie**  
  
  **Compilateur d'optimisation Microsoft \(R\) C\/C\+\+ version 17.00.50727.1 pour x86**  
**Copyright \(c\) Microsoft Corporation.  Tous droits réservés.  simple.c**  
**Microsoft \(R\) Incremental Linker Version 11.00.50727.1**  
**Copyright \(c\) Microsoft Corporation.  Tous droits réservés.  \/out:simple.exe**  
**simple.obj**      Le numéro de version des outils dépend de la version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] et des mises à jour éventuelles que vous avez installées.  
  
    > [!NOTE]
    >  Si vous recevez une erreur comme « cl' n'est pas reconnu en tant que commande interne ou externe, programme exécutable ou fichier de commandes », l'erreur C1034 ou l'erreur LNK1104, vous devez définir l'environnement pour le compilateur et les outils.  Pour plus d'informations, consultez l'étape 1.  
    >   
    >  Si vous recevez une erreur ou un avertissement du compilateur, recherchez les erreurs dans votre code source, puis enregistrez\-le et réexécutez le compilateur.  Pour plus d'informations sur des erreurs spécifiques, utilisez la zone de recherche sur cette page.  
  
8.  Pour exécuter votre programme, tapez son nom sans l'extension de nom de fichier, par exemple **simple**, puis appuyez sur Entrée.  
  
     Le programme affiche ce texte puis se ferme :  
  
     `This is a native C program.`  
  
## Voir aussi  
 [Procédure pas à pas : création d'un programme console Win32 \(C\+\+\)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)   
 [Référence du langage C](../c-language/c-language-reference.md)   
 [Génération de programmes C\/C\+\+](../build/building-c-cpp-programs.md)   
 [Compatibilité](../c-runtime-library/compatibility.md)