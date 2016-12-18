---
title: "/WX (Traiter les avertissements de l&#39;&#201;diteur de liens comme des erreurs) | Microsoft Docs"
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
  - "/WX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WX (option de l'éditeur de liens)"
  - "WX (option de l'éditeur de liens)"
  - "-WX (option de l'éditeur de liens)"
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WX (Traiter les avertissements de l&#39;&#201;diteur de liens comme des erreurs)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/WX[:NO]  
```  
  
## Notes  
 L'option \/WX spécifie qu'aucun fichier de sortie n'est créé lorsque l'Éditeur de liens génère un avertissement.  
  
 Cela est comparable à **\/WX** pour le compilateur \(voir [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(Niveau d'avertissement\)](../../build/reference/compiler-option-warning-level.md) pour plus d'informations\).  Toutefois, spécifier **\/WX** pour la compilation n'implique pas que **\/WX** soit également actif lors de la phase de liaison ; vous devez spécifier explicitement **\/WX** pour chaque outil.  
  
 Par défaut, l'option **\/WX** n'est pas activée.  Pour traiter les avertissements de l'éditeur de liens comme des erreurs, spécifiez **\/WX**.  **\/WX:NO** équivaut à ne pas spécifier **\/WX**.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)