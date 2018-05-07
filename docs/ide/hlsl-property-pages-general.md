---
title: 'Pages de propriétés HLSL : Général | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs:
- C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77cc9a44076999633fd17b049cbcfad75f65eb7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="hlsl-property-pages-general"></a>Pages de propriétés HLSL : Général
Pour configurer les propriétés suivantes du compilateur HLSL (fxc.exe), utilisez son **général** page de propriétés. Pour plus d’informations sur l’accès à la **général** page de propriétés dans le dossier HLSL, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Autres répertoires Include**  
 Ajoute un ou plusieurs répertoires pour le chemin d’accès include. Utilisez des points-virgules pour séparer les répertoires.  
  
 Cette propriété correspond à la **/I [path]** argument de ligne de commande.  
  
 **Nom de point d’entrée**  
 Spécifie le point d’entrée pour le nuanceur. Par défaut, la valeur est **principal**.  
  
 Cette propriété correspond à la **/E [nom]** argument de ligne de commande.  
  
 **Désactiver les optimisations**  
 **Oui (/ Od)** pour désactiver les optimisations ; sinon, **non**. Par défaut, la valeur est **Oui (/ Od)** pour **déboguer** configurations et **non** pour **version** configurations.  
  
 Le **/Od** un argument de ligne de commande du compilateur HLSL applique implicitement la **/GFP, même** argument de ligne de commande, mais une sortie ne pas être identique à la sortie qui est généré en passant à la fois le **/Od**  et **/GFP, même** des arguments de ligne de commande explicitement.  
  
 **Activer les informations de débogage**  
 **Oui (/ Zi)** pour activer les informations de débogage ; sinon, **non**. Par défaut, la valeur est **Oui (/ Zi)** pour **déboguer** configurations et **non** pour **version** configurations.  
  
 **Type de nuanceur**  
 Spécifie le type de nuanceur. Différents types de nuanceurs implémentent différentes parties du pipeline graphique. Certains types de nuanceurs sont uniquement disponibles dans les modèles de nuanceur les plus récentes (qui sont spécifié par le **Shader Model** propriété) : par exemple, calculer les nuanceurs ont été introduites dans le modèle de nuanceur 5.  
  
 Cette propriété correspond à la **[type]** partie de la **/T [type] _ [modèle]** des arguments de ligne de commande du compilateur HLSL. Le **modèles de nuanceur** propriété spécifie le **[modèle]** partie de l’argument.  
  
 **Modèle de nuanceur**  
 Spécifie le modèle de nuanceur. Modèles de nuanceur différentes ont des fonctions différentes. En général, plus les modèles de nuanceur offrent des fonctionnalités étendues, mais nécessitent plus moderne matériel graphique pour exécuter le code du nuanceur. Certains types de nuanceurs (qui sont spécifié par le **Type de nuanceur** propriété) sont uniquement disponibles dans les modèles de nuanceur les plus récentes, de calcul, par exemple, les nuanceurs ont été introduites dans le modèle de nuanceur 5.  
  
 Cette propriété correspond à la **[modèle]** partie de la **/T [type] _ [modèle]** des arguments de ligne de commande du compilateur HLSL. Le **Type de nuanceur** propriété spécifie le **[type]** partie de l’argument.  
  
 **Définitions de préprocesseur**  
 Ajoute une ou plusieurs définitions de symbole de préprocesseur à appliquer au fichier de code source HLSL. Utilisez des points-virgules pour séparer les définitions de symbole.  
  
 Cette propriété correspond à la **/D [définitions]** des arguments de ligne de commande du compilateur HLSL.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés HLSL](../ide/hlsl-property-pages.md)   
 [Pages de propriétés HLSL : avancé](../ide/hlsl-property-pages-advanced.md)   
 [HLSL, page de propriétés : fichiers de sortie](../ide/hlsl-property-pages-output-files.md)