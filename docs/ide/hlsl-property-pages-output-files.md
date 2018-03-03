---
title: "Pages de propriétés HLSL : Fichiers de sortie | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
dev_langs:
- C++
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04f6ad8889c9a713b3b64284b329c21d5a2cd49e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="hlsl-property-pages-output-files"></a>Pages de propriétés HLSL : fichiers de sortie
Pour configurer les propriétés suivantes du compilateur HLSL (fxc.exe), utilisez son **fichiers de sortie** propriété. Pour plus d’informations sur l’accès à la **fichiers de sortie** page de propriétés dans le dossier HLSL, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Nom de Variable d’en-tête**  
 Spécifie le nom d’un tableau qui est utilisé pour du code HLSL objet encodé. Le tableau est contenu dans un fichier d’en-tête qui est générée par le compilateur HLSL. Le nom du fichier d’en-tête est spécifié par le **nom de fichier d’en-tête** propriété.  
  
 Cette propriété correspond à la **/Vn [name]** argument de ligne de commande.  
  
 **Nom de fichier d’en-tête**  
 Spécifie le nom du fichier d’en-tête généré par le compilateur HLSL. L’en-tête contient du code HLSL objet qui est codé dans un tableau. Le nom du tableau est spécifié par le **nom de la Variable en-tête** propriété.  
  
 Cette propriété correspond à la **/Fh [name]** argument de ligne de commande.  
  
 **Nom de fichier objet**  
 Spécifie le nom du fichier objet qui est générée par le compilateur HLSL. Par défaut, la valeur est **.cso de % (Filename) $(OutDir)**.  
  
 Cette propriété correspond à la **/Fo [name]** argument de ligne de commande.  
  
 **Sortie de l’assembleur**  
 **Listing assembleur uniquement (/ Fc)** pour simplement les instructions de langage d’assembly de sortie. **Code de l’assembly et Hex (/ Fx)** vers la sortie des instructions de langage d’assembly et le code d’opération correspondant au format hexadécimal. Par défaut, aucune annonce n’est sortie.  
  
 **Fichier de sortie assembleur**  
 Spécifie le nom du fichier d’assembly liste générée par le compilateur HLSL.  
  
 Cette propriété correspond à la **/Fc [nom]** et **/Fx [nom]** des arguments de ligne de commande.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés HLSL](../ide/hlsl-property-pages.md)   
 [Pages de propriétés HLSL : général](../ide/hlsl-property-pages-general.md)   
 [HLSL, page de propriétés : Avancé](../ide/hlsl-property-pages-advanced.md)