---
title: "Pages de propri&#233;t&#233;s HLSL&#160;: G&#233;n&#233;ral | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.FXCompilerTool.ShaderModel"
  - "VC.Project.FXCompilerTool.PreprocessorDefinitions"
  - "VC.Project.FXCompilerTool.ShaderType"
  - "VC.Project.FXCompilerTool.EnableDebuggingInformation"
  - "VC.Project.FXCompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.FXCompilerTool.DisableOptimizations"
  - "VC.Project.FXCompilerTool.EntryPointName"
dev_langs: 
  - "C++"
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
caps.latest.revision: 8
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 8
---
# Pages de propri&#233;t&#233;s HLSL&#160;: G&#233;n&#233;ral
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour configurer les propriétés suivantes du compilateur de HLSL \(fxc.exe\), utilisez sa page de propriétés **Général** .  Pour plus d'informations sur l'accès à la page de propriétés **Général** dans le dossier de HLSL, consultez [Comment : spécifier des propriétés de projet avec des pages de propriétés](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
## Liste UIElement  
 **Répertoires Include supplémentaires**  
 Ajoute un ou plusieurs dossiers au chemin d'accès Include.  Points\-virgules d'utilisation pour séparer les dossiers.  
  
 Cette propriété correspond à l'argument de ligne de commande des **\/I\[path\]** .  
  
 **Nom d'Entrée**  
 Spécifie le point d'entrée pour le shader.  Par défaut, la valeur est **Principal**.  
  
 Cette propriété correspond à l'argument de ligne de commande des **\/E\[name\]** .  
  
 **Désactiver des optimisations**  
 **Oui \(\/Od\)** pour désactiver des optimisations ; sinon, **Non**.  Par défaut, la valeur est **Oui \(\/Od\)** pour les paramètres et **NonDéboguer** pour les paramètres **Version finale** .  
  
 L'argument de ligne de commande des **\/Od** au compilateur de HLSL applique implicitement l'argument de ligne de commande des **\/Gfp**, mais sortie ne peut pas être identique à la sortie qui est produite lors de le passage des arguments de ligne de commande des **\/Od** et d' **\/Gfp** explicitement.  
  
 **Activez les informations de débogage**  
 **Oui \(\/Zi\)** pour activer les informations de débogage ; sinon, **Non**.  Par défaut, la valeur est **Oui \(\/Zi\)** pour les paramètres et **NonDéboguer** pour les paramètres **Version finale** .  
  
 **Type de nuanceur**  
 Spécifie le genre de shader.  Les différents types de shaders implémentent les différentes parties du pipeline de graphiques.  Certains types de shaders sont uniquement disponibles dans les modèles shaders plus récents \(spécifiés par la propriété **Modèle de nuanceur** \) pour l'exemple, shaders de calcul a été introduit dans le model\) 5. de shader.  
  
 Cette propriété correspond à la partie d' **\[type\]** de l'argument de ligne de commande des **\/T \[type\]\_\[model\]** au compilateur de HLSL.  La propriété **Modèles shaders** spécifie la partie d' **\[model\]** de l'argument.  
  
 **Modèle de nuanceur**  
 Spécifie le modèle de nuanceur.  Les différents modèles shaders ont des fonctions.  En général une publication shadère plus récente de modèles est développée des fonctions mais requiert un matériel vidéo plus récent d'exécuter du code shader.  Certains types de shaders \(spécifiés par la propriété **Type de nuanceur** \) sont uniquement disponibles dans un shader plus récent modèle\- pour l'exemple, shaders de calcul a été introduit dans le model\) 5. de shader.  
  
 Cette propriété correspond à la partie d' **\[model\]** de l'argument de ligne de commande des **\/T \[type\]\_\[model\]** au compilateur de HLSL.  La propriété **Type de nuanceur** spécifie la partie d' **\[type\]** de l'argument.  
  
 **Définitions de préprocesseur**  
 Ajoute une ou plusieurs définitions de symbole de préprocesseur pour appliquer au fichier de code source de HLSL.  Points\-virgules d'utilisation pour séparer les définitions de symbole.  
  
 Cette propriété correspond à l'argument de ligne de commande des **\/D \[definitions\]** au compilateur de HLSL.  
  
## Voir aussi  
 [Pages de propriétés HLSL](../ide/hlsl-property-pages.md)   
 [Pages de propriétés HLSL : Avancé](../ide/hlsl-property-pages-advanced.md)   
 [Pages de propriétés HLSL : fichiers de sortie](../ide/hlsl-property-pages-output-files.md)