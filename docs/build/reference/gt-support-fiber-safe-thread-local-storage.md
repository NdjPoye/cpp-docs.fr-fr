---
title: "/GT (Prendre en charge le stockage local des threads avec fibres s&#233;curis&#233;es) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations"
  - "/gt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GT (option du compilateur C++)"
  - "stockage local des threads de type statique à fibres sécurisées (option du compilateur C++)"
  - "GT (option du compilateur C++)"
  - "-GT (option du compilateur C++)"
  - "stockage local des threads de type statique et sécurité des fibres"
  - "stockage local des threads"
ms.assetid: 071fec79-c701-432b-9970-457344133159
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GT (Prendre en charge le stockage local des threads avec fibres s&#233;curis&#233;es)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge la sécurité des fibres pour les données allouées à l'aide d'un stockage local des threads de type statique, c'est\-à\-dire des données allouées avec `__declspec(thread)`.  
  
## Syntaxe  
  
```  
/GT  
```  
  
## Notes  
 Les données déclarées avec `__declspec(thread)` sont référencées via un tableau de stockage local des threads \(TLS, Thread\-Local Storage\).  Le tableau TLS est un tableau d'adresses que le système gère pour chaque thread.  Dans ce tableau, chaque adresse indique l'emplacement des données de stockage local des threads.  
  
 Une fibre est un objet léger, composé d'une pile et d'un contexte de registre, qui peut être planifié sur différents threads.  Une fibre peut être exécutée sur n'importe quel thread.  Dans la mesure où une fibre peut être transférée et redémarrée ultérieurement sur un autre thread, l'adresse du tableau TLS ne doit pas être mise en cache ni optimisée en tant que sous\-expression commune dans un appel de fonction \(pour plus d'informations, consultez l'option [\/Og \(Optimisations globales\)](../../build/reference/og-global-optimizations.md)\).  **\/GT** empêche ce type d'optimisation.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Activation des optimisations à fibres sécurisées**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)