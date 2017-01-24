---
title: "/GR (Activer les informations de type au moment de l&#39;ex&#233;cution) | Microsoft Docs"
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
  - "/gr"
  - "VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo"
  - "VC.Project.VCCLCompilerTool.RuntimeTypeInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gr (option du compilateur C++)"
  - "activer RTTI (option du compilateur C++)"
  - "Gr (option du compilateur C++)"
  - "-Gr (option du compilateur C++)"
  - "RTTI (option du compilateur)"
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GR (Activer les informations de type au moment de l&#39;ex&#233;cution)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute le code permettant de vérifier les types d'objet au moment de l'exécution.  
  
## Syntaxe  
  
```  
/GR[-]  
```  
  
## Notes  
 Lorsque **\/GR** est activé, le compilateur définit la macro du préprocesseur `_CPPRTTI`.  **\/GR** est activé par défaut.  **\/GR\-** désactive les informations de type au moment de l'exécution.  
  
 Utilisez **\/GR** si le compilateur ne peut pas résoudre statiquement de type d'objet dans votre code.  Vous avez habituellement besoin de l'option **\/GR** lorsque votre code utilise [dynamic\_cast, opérateur](../../cpp/dynamic-cast-operator.md) ou [typeid](../../cpp/typeid-operator.md).  Toutefois, **\/GR** augmente la taille des sections .rdata de votre image.  Si votre code n'utilise pas **dynamic\_cast** ou **typeid**, **\/GR\-** peut produire une image plus petite.  
  
 Pour plus d'informations sur la vérification des types au moment de l'exécution, consultez [Informations de type au moment de l'exécution](../../cpp/run-time-type-information.md) dans le *Guide de référence du langage C\+\+*.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Langue**.  
  
4.  Modifiez la propriété **Activation des informations de type au moment de l'exécution**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)