---
title: "Sp&#233;cification des outils de g&#233;n&#233;ration personnalis&#233;e | Microsoft Docs"
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
  - "VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets"
  - "VC.Project.VCCustomBuildTool.Outputs"
  - "VC.Project.VCCustomBuildTool.Command"
  - "VC.Project.VCCustomBuildTool.CommandLine"
  - "VC.Project.VCCustomBuildTool.AdditionalDependencies"
  - "VC.Project.VCCustomBuildTool.Message"
  - "VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets"
  - "VC.Project.VCCustomBuildTool.Description"
  - "VC.Project.VCCustomBuildTool.AdditionalInputs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "outils de génération (C++), spécifier"
  - "générations (C++), outils de génération personnalisée"
  - "outils de génération personnalisée (C++), spécifier"
ms.assetid: e5161946-8002-418d-991e-219e6a8586f5
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Sp&#233;cification des outils de g&#233;n&#233;ration personnalis&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un *outil de génération personnalisée* fournit au système de génération les informations dont il a besoin pour générer des fichiers d'entrée spécifiques.  Un outil de génération personnalisée spécifie une commande à exécuter, une liste de fichiers d'entrée, une liste de fichiers de sortie générés par la commande, ainsi qu'une description facultative de l'outil.  
  
 Pour obtenir des informations générales sur les outils de génération personnalisée et les étapes de build personnalisée, consultez [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md).  
  
### Pour spécifier un outil de génération personnalisée  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../ide/working-with-project-properties.md).  
  
2.  Cliquez sur **Propriétés de configuration** pour activer la zone **Configuration**.  Dans la zone **Configuration**, sélectionnez la configuration pour laquelle vous voulez spécifier un outil de génération personnalisée.  
  
3.  Dans l'**Explorateur de solutions**, sélectionnez le fichier d'entrée pour l'outil de génération personnalisée.  
  
     Si le dossier **Outil de génération personnalisée** ne s'affiche pas, cela signifie que l'extension du fichier que vous avez sélectionné est associée à un outil par défaut.  Par exemple, le compilateur est l'outil par défaut associé aux fichiers .c et .cpp.  Pour substituer un paramètre d'outil par défaut, dans le nœud **Propriétés de configuration**, dans le dossier **Général**, cliquez sur **Outil de génération personnalisée** dans la propriété **Type d'élément**.  Cliquez sur **Appliquer** pour afficher le nœud **Outil de génération personnalisée**.  
  
4.  Dans le nœud **Outil de génération personnalisée**, dans le dossier **Général**, spécifiez les propriétés associées à l'outil de génération personnalisée :  
  
    -   Dans **Dépendances supplémentaires**, spécifiez d'autres fichiers en plus de celui pour lequel l'outil de génération personnalisée est défini \(le fichier associé à l'outil de génération personnalisée est implicitement considéré comme entrée pour l'outil\).  Un outil de génération personnalisée ne nécessite pas obligatoirement l'existence de fichiers d'entrée supplémentaires.  Si vous disposez de plusieurs fichiers d'entrée, séparez\-les par des points\-virgules.  
  
         Si la date d'un fichier **Dépendances supplémentaires** est postérieure à celle du fichier d'entrée, l'outil de génération personnalisée est alors exécuté.  Si tous les fichiers **Dépendances supplémentaires** sont plus anciens que le fichier d'entrée et que le fichier d'entrée est plus ancien que le fichier de propriétés **Sorties**, l'outil de génération personnalisée n'est pas exécuté.  
  
         Par exemple, supposons que vous disposiez d'un outil de génération personnalisée utilisant MyInput.x en entrée et générant MyInput.cpp, et que MyInput.x inclut le fichier d'en\-tête MyHeader.h.  Vous pouvez spécifier MyHeader.h comme dépendance d'entrée pour MyInput.x et le système de génération générera MyInput.cpp lorsqu'il n'est plus à jour par rapport à MyInput.x ou MyHeader.h.  
  
         Les dépendances d'entrée peuvent également garantir l'exécution de vos outils de génération personnalisée dans l'ordre que vous voulez.  Supposons, en reprenant l'exemple précédent, que MyHeader.h soit en fait la sortie d'un outil de génération personnalisée.   Dans la mesure où MyHeader.h est une dépendance de MyInput.x, le système de génération génère d'abord MyHeader.h avant d'exécuter l'outil de génération personnalisée sur MyInput.x.  
  
    -   Dans **Ligne de commande**, spécifiez une commande comme vous le feriez à une invite de commandes.  Spécifiez une commande ou un fichier de commandes valide, ainsi que les fichiers d'entrée ou de sortie requis.  Spécifiez la commande batch **call** avant le nom d'un fichier de commandes pour garantir l'exécution de toutes les commandes suivantes.  
  
         Il est possible de spécifier plusieurs fichiers d'entrée et de sortie symboliquement à l'aide de macros MSBuild.  [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)] la spécification de l'emplacement de fichiers ou de noms de jeux de fichiers, consultez [Macros pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md).  
  
         Dans la mesure où le caractère « % » est réservé à MSBuild, lorsque vous spécifiez une variable d'environnement, il convient de remplacer chaque caractère d'échappement **%** par la séquence d'échappement hexadécimale **%25**.  Par exemple, remplacez **%WINDIR%** par **%25WINDIR%25**.  MSBuild remplace chaque séquence **%25** par le caractère **%** avant d'accéder à la variable d'environnement.  
  
    -   Dans la zone **Description**, tapez un message décrivant cet outil de génération personnalisée.  Ce message est imprimé dans la fenêtre **Sortie** lorsque le système de génération traite cet outil.  
  
    -   Dans **Outputs**, spécifiez le nom du fichier de sortie.  Cette entrée est requise ; si aucune valeur n'est définie pour cette propriété, l'outil de génération personnalisée ne s'exécutera pas.  Si un outil de génération personnalisée comporte plusieurs sorties, séparez les noms de fichiers par un point\-virgule.  
  
         Le nom du fichier de sortie doit correspondre au nom spécifié dans la propriété **Ligne de commande**.  Le système de génération de projet recherchera le fichier et vérifiera sa date.  Si le fichier de sortie est plus récent que le fichier d'entrée ou si le fichier de sortie est introuvable, l'outil de génération personnalisée est exécuté.  Si tous les fichiers **Dépendances supplémentaires** sont plus anciens que le fichier d'entrée et que le fichier d'entrée est plus ancien que le fichier spécifié dans la propriété **Sorties**, l'outil de génération personnalisée n'est pas exécuté.  
  
 Si vous voulez que le système de génération traite un fichier de sortie généré par l'outil de génération personnalisée, vous devez l'ajouter manuellement au projet.  L'outil de génération personnalisée mettra à jour le fichier pendant la génération.  
  
## Exemple  
 Supposez que vous vouliez inclure dans votre projet un fichier nommé parser.l.  Vous voulez qu'un analyseur lexical traite parser.l pour produire un fichier .c portant le même nom de base \(parser.c\).  
  
 Dans un premier temps, ajoutez parser.l et parser.c au projet.  Si les fichiers n'existent pas encore, ajoutez simplement une référence à ces fichiers.  Vous créez un outil de génération personnalisée pour parser.l et tapez l'information suivante dans la propriété **Commandes** :  
  
```  
lexer %(FullPath) .\%(Filename).c  
```  
  
 Cette commande exécutera l'analyseur lexical sur parser.l et produira en sortie parser.c dans le répertoire du projet.  
  
 Dans la propriété **Outputs**, tapez le texte suivant :  
  
```  
.\%(Filename).c  
```  
  
 Lorsque vous générez le projet, le système de génération compare les horodatages de parser.l et parser.c.  Si parser.l est plus récent ou si parser.c n'existe pas, le système de génération exécute la valeur de la propriété **Ligne de commande** pour actualiser parser.c.  Comme parser.c a également été ajouté au projet, le système de génération procède alors à la compilation de parser.c.  
  
## Voir aussi  
 [Macros pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md)   
 [Dépannage des personnalisations de génération](../ide/troubleshooting-build-customizations.md)