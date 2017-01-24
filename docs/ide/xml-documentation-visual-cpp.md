---
title: "Documentation&#160;XML (Visual&#160;C++) | Microsoft Docs"
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
  - "/// délimiteur pour les balises de documentation C++"
  - "commentaires, fichiers de code source C++"
  - "documentation XML"
  - "XML, commentaires de documentation dans le code source"
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Documentation&#160;XML (Visual&#160;C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans Visual C\+\+, vous pouvez ajouter des commentaires à votre code source qui sera traité dans un fichier .xml.  Ce fichier peut ensuite être l'entrée à un processus qui crée la documentation pour les classes dans votre code.  
  
 Dans Visual C\+\+ un fichier de code, des commentaires de documentation XML doivent être installés directement avant une méthode ou une définition de type.  Les commentaires peuvent être utilisés pour renseigner fin de données Intellisense info express dans les scénarios suivants :  
  
1.  lorsque le code est compilé en tant que composant d'exécution windows avec un fichier accompagnant de .winmd  
  
2.  lorsque le code source est inclus dans le projet actuel  
  
3.  dans une bibliothèque dont les déclarations de type et les implémentations se trouvent dans le même fichier d'en\-tête  
  
> [!NOTE]
>  Dans la version actuelle, les commentaires du code ne sont pas traités sur des modèles ou n'importe quoi contenant un type de modèle \(par exemple, une fonction prenant un paramètre comme modèle\).  Ajout de ces commentaires entraîne le comportement non défini.  
  
 Pour plus d'informations sur la création d'un fichier .xml avec des commentaires de documentation, consultez les rubriques suivantes.  
  
|Pour plus d'informations sur|Consultez|  
|----------------------------------|---------------|  
|Les options du compilateur à utiliser|[\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|Balises que vous pouvez utiliser pour fournir aux fonctionnalités couramment utilisées dans la documentation|[Balises recommandées pour commentaires de documentation](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|Les chaînes d'ID que le compilateur produit pour identifier les éléments dans votre code|[Traiter le fichier .xml](../ide/dot-xml-file-processing.md)|  
|Procédure et délimitent les balises de documentation|[Séparateurs pour les balises de documentation Visual C\+\+](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|Générer un fichier .xml à partir d'un ou plusieurs fichiers .xdc.|[Référence de XDCMake](../ide/xdcmake-reference.md)|  
|Liens vers des informations sur XML par rapport à les fonctionnalités de Visual Studio|[XML dans Visual Studio](../Topic/XML%20Tools%20in%20Visual%20Studio.md)|  
  
 Si vous devez placer des caractères spéciaux XML dans le texte de commentaire de documentation, vous devez utiliser des entités XML ou une section CDATA.  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)