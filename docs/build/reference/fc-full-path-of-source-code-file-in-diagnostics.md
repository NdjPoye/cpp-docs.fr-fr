---
title: "/FC (Chemin d&#39;acc&#232;s complet du fichier de code source dans les diagnostics) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.UseFullPaths"
  - "/FC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FC (option du compilateur C++)"
  - "-FC (option du compilateur C++)"
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FC (Chemin d&#39;acc&#232;s complet du fichier de code source dans les diagnostics)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Demande au compilateur d'afficher le chemin d'accès complet des fichiers de code source passés au compilateur dans le diagnostic.  
  
## Syntaxe  
  
```  
/FC  
```  
  
## Notes  
 Prenons l'exemple de code suivant :  
  
```  
// compiler_option_FC.cpp  
int main( ) {  
   int i   // C2143  
}  
```  
  
 Sans **\/FC**, le texte de diagnostic ressemblera au suivant :  
  
-   compiler\_option\_FC.cpp\(5\) : erreur C2143 : erreur de syntaxe : absence de ';' avant '}'  
  
 Avec **\/FC**, le texte de diagnostic ressemblera au suivant :  
  
-   c:\\test\\compiler\_option\_FC.cpp\(5\) : erreur de syntaxe : absence de ';' avant '}'  
  
 **\/FC** est également nécessaire si vous souhaitez afficher le chemin d'accès complet d'un nom de fichier lors de l'utilisation de la macro \_\_FILE\_\_.  Pour plus d'informations sur \_\_FILE\_\_, consultez [Macros prédéfinies](../../preprocessor/predefined-macros.md).  
  
 L'option **\/FC** est impliquée par **\/ZI**.  Pour plus d'informations sur **\/ZI**, consultez [\/Z7, \/Zi, \/ZI \(Format des informations de débogage\)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **C\/C\+\+**.  
  
4.  Sélectionnez la page de propriétés **Avancé**.  
  
5.  Modifiez la propriété **Utilisation des chemins d'accès complets**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)