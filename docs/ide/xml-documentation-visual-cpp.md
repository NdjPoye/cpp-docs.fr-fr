---
title: Documentation XML (Visual C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17853a43d3a94be779b659b0da825467fa66f61c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="xml-documentation-visual-c"></a>Documentation XML (Visual C++)
Dans Visual C++, vous pouvez ajouter des commentaires à votre code source qui sera traitée dans un fichier .xml. Ce fichier peut ensuite être l’entrée à un processus qui crée la documentation pour les classes dans votre code.  
  
 Dans un fichier de code Visual C++, les commentaires de documentation XML doivent être placés directement avant une définition de méthode ou un type. Les commentaires peuvent être utilisés pour remplir la bulle Intellisense QuickInfo dans les scénarios suivants :  
  
1.  Lorsque le code est compilé en tant qu’un composant Windows Runtime avec un fichier .winmd  
  
2.  Lorsque le code source est inclus dans le projet actuel  
  
3.  dans une bibliothèque dont les déclarations de type et des implémentations sont situées dans le même fichier d’en-tête  
  
> [!NOTE]
>  Dans la version actuelle, les commentaires de code ne sont pas traités sur des modèles ou de tout élément contenant un type de modèle (par exemple, une fonction prend un paramètre comme modèle). L’ajout de ces commentaires entraîne un comportement non défini.  
  
 Pour plus d’informations sur la création d’un fichier .xml avec les commentaires de documentation, consultez les rubriques suivantes.  
  
|Pour obtenir des informations sur|Voir|  
|---------------------------|---------|  
|Les options du compilateur à utiliser|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|Les balises que vous pouvez utiliser pour fournir couramment utilisé la fonctionnalité de documentation|[Balises recommandées pour les commentaires de documentation](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|Les chaînes d’identification générées par le compilateur pour identifier les constructions dans votre code|[Traitement du fichier .xml](../ide/dot-xml-file-processing.md)|  
|Comment faire pour délimiter les balises de documentation|[Délimiteurs pour les étiquettes de documentation Visual C++](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|Génération d’un fichier .xml à partir d’un ou plusieurs fichiers .xdc.|[Informations de référence sur XDCMake](../ide/xdcmake-reference.md)|  
|Des liens vers des informations sur XML, tel qu’il est lié à certaines fonctionnalités de Visual Studio|[XML dans Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)|  
  
 Si vous devez placer les caractères spéciaux XML dans le texte d’un commentaire de documentation, vous devez utiliser des entités XML ou une section CDATA.  
  
## <a name="see-also"></a>Voir aussi  
 [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)