---
title: "Fichier JScript | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "AddConfig (méthode)"
  - "AddFilesToCustomProj (méthode)"
  - "AddFilters (méthode)"
  - "Common.js (fichier)"
  - "CreateCustomInfFile (méthode)"
  - "CreateCustomProject (méthode)"
  - "Assistants personnalisés, accéder au modèle d'objet de l'Assistant"
  - "Assistants personnalisés, fichier JScript"
  - "déboguer (JScript), activer le débogage de scripts"
  - "déboguer (JScript), fichiers JScript"
  - "script de débogage"
  - "script de débogage, activer le débogage de scripts"
  - "fichier Default.js"
  - "DelFile (méthode)"
  - "fichiers (C++), créés par l'Assistant personnalisé"
  - "GetTargetName (méthode)"
  - "fichiers JScript"
  - "OnFinish (méthode)"
  - "PchSettings (méthode)"
ms.assetid: 7841a09e-2dd2-4f1a-a13a-39ac53f24315
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichier JScript
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'[Assistant personnalisé](../ide/custom-wizard.md) accède au moteur de script et crée un fichier JScript appelé Default.js pour chaque projet.  Il inclut aussi [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md).  Ces fichiers contiennent des fonctions JScript permettant d'accéder aux modèles objet Visual Studio et Visual C\+\+ pour personnaliser un Assistant.  \(Consultez [Conception d'un Assistant](../ide/designing-a-wizard.md) pour une liste de ces modèles\). Vous pouvez ajouter vos fonctions au fichier Default.js du projet d'Assistant.  Pour accéder aux propriétés et méthodes du modèle objet d'Assistant ou d'environnement à partir d'un fichier JScript, faites précéder le nom du modèle objet respectivement de « wizard. » et « dte. ».  
  
 Par exemple :  
  
```  
function CreateCustomProject(strProjectName, strProjectPath)  
{  
   try  
   {  
      var strProjTemplatePath = wizard.FindSymbol('PROJECT_TEMPLATE_PATH');  
var strProjTemplate = '';  
      strProjTemplate = strProjTemplatePath + '\\default.vcproj';  
  
      var Solution = dte.Solution;  
      var strSolutionName = "";  
      if (wizard.FindSymbol("CLOSE_SOLUTION"))  
...  
```  
  
 Quand vous cliquez sur **Terminer** dans l'[Assistant personnalisé](../ide/custom-wizard.md), l'Assistant crée le fichier Default.js dans le dossier des fichiers de script de l'Explorateur de solutions.  Ce fichier JScript crée des projets et restitue des modèles, puis les ajoute à la solution quand un utilisateur clique sur **Terminer** dans votre Assistant.  
  
 Par défaut, le fichier Default.js du projet inclut les fonctions suivantes :  
  
|Nom de la fonction|Description|  
|------------------------|-----------------|  
|**AddConfig**|Ajoute les configurations du projet.  Vous pouvez fournir des paramètres de compilateur et d'éditeur de lien.|  
|**AddFilesToCustomProj**|Ajoute les fichiers spécifiés au projet quand l'utilisateur clique sur **Terminer**.|  
|**AddFilters**|Ajoute les filtres sources spécifiés au projet quand l'utilisateur clique sur **Terminer**.|  
|**CreateCustomProject**|Crée le projet à l'emplacement spécifié quand l'utilisateur clique sur **Terminer**.|  
|**CreateCustomInfFile**|Crée le [fichier Templates.inf](../ide/templates-inf-file.md) du fichier.|  
|**DelFile**|Supprime le fichier spécifié.|  
|**GetTargetName**|Donne le nom du fichier spécifié.|  
|**OnFinish**|Appelé par l'Assistant quand l'utilisateur clique sur **Terminer** pour créer le projet, ajouter les fichiers et les filtres, restituer les modèles et définir la configuration.|  
|**PchSettings**|Définit les paramètres de l'en\-tête précompilé.  Consultez [SetCommonPchSettings](../ide/setcommonpchsettings.md) dans le Guide de référence de Common.js pour plus d'informations.|  
  
 Chaque Assistant utilise un fichier Default.js unique, qui inclut des commentaires TODO pour vous aider à identifier les endroits où vous devez personnaliser le fichier.  
  
 Visual C\+\+ inclut aussi [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md), fichier partagé par tous les Assistants et inclus dans votre projet d'Assistant.  Vous pouvez utiliser les fonctions de Common.js.  
  
> [!NOTE]
>  Common.js contient des descriptions de chaque fonction et de ses paramètres.  Consultez les commentaires de Common.js pour plus d'informations.  
  
 Si vous avez des fonctions que vous souhaitez partager entre vos projets d'Assistant, vous pouvez les ajouter à Common.js.  Créez votre propre version de Common.js et enregistrez\-la dans un chemin d'accès commun, puis affectez au SCRIPT\_COMMON\_PATH ce chemin d'accès dans votre [fichier .vsz](../ide/dot-vsz-file-project-control.md).  
  
> [!NOTE]
>  Les Assistants inclus avec Visual C\+\+ utilisent les fonctions JScript dans Common.js.  Si vous modifiez ces fonctions, les Assistants de Visual C\+\+ peuvent se comporter de façon inattendue.  
  
 Pour plus d'informations sur JScript, consultez [Writing, Compiling, and Debugging JScript Code](http://msdn.microsoft.com/fr-fr/13e57e7d-4867-4555-b9e4-fc24aa75e628).  
  
## Débogage de script  
 Pour déboguer un script dans des fichiers html de l'Assistant, vous devez activer la fonction de débogage de script.  
  
#### Pour activer le débogage de script  
  
1.  Dans Internet Explorer, cliquez sur le menu **Outils** puis sur **Options Internet**.  
  
2.  Cliquez sur l'onglet **Avancés**.  
  
3.  Dans la catégorie **Navigation**, désactivez la case à cocher **Désactiver le débogueur de script**.  
  
 Les fichiers common.js et default.js s'afficheront ainsi dans la fenêtre **Documents en cours d'exécution** lorsque vous cliquerez sur le bouton Terminer de l'Assistant.  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)