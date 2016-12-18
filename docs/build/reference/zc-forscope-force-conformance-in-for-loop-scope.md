---
title: "/Zc:forScope (Forcer la conformit&#233; &#224; la port&#233;e de la boucle for) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope"
  - "VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope"
  - "/zc:forScope"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (option du compilateur C++)"
  - "conformité des options du compilateur"
  - "Zc (option du compilateur C++)"
  - "-Zc (option du compilateur C++)"
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:forScope (Forcer la conformit&#233; &#224; la port&#233;e de la boucle for)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet d'implémenter un comportement C\+\+ standard pour les boucles [for](../../cpp/for-statement-cpp.md) avec les extensions Microsoft \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).**\/Zc:forScope** est activé par défaut.  
  
## Syntaxe  
  
```  
/Zc:forScope[-]  
```  
  
## Notes  
 L’option **\/Zc:forScope\-** est déconseillée et sera supprimée dans une version ultérieure. L’utilisation de **\/Zc:forScope\-** génère l’avertissement D9035 de désapprobation.  
  
 Le comportement standard consiste à laisser l’initialiseur d’une boucle **for** sortir de la portée après la boucle **for**. Sous **\/Zc:forScope\-** et [\/Ze](../../build/reference/za-ze-disable-language-extensions.md), l’initialiseur de la boucle **for** reste dans la portée jusqu’à la fin de la portée locale.  
  
 Le code suivant est compilé sous **\/Ze**, mais pas sous **\/Za** :  
  
```cpp  
// zc_forScope.cpp  
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp  
// C2065, D9035 expected  
int main() {  
    // Compile by using cl /Zc:forScope- zc_forScope.cpp  
    // to compile this non-standard code as-is.  
    // Uncomment the following line to resolve C2065 for /Za.  
    // int i;  
    for (int i = 0; i < 1; i++)  
        ;  
    i = 20;   // i has already gone out of scope under /Za  
}  
```  
  
 Si vous utilisez **\/Zc:forScope\-**, l’avertissement C4288 \(désactivé par défaut\) est généré si une variable est dans la portée en raison de l’existence d’une déclaration dans une portée précédente. Pour illustrer ceci, supprimez les caractères `//` dans l’exemple de code pour déclarer `int i`.  
  
 Vous pouvez modifier le comportement au moment de l’exécution de **\/Zc:forScope** en utilisant le pragma [conform](../../preprocessor/conform.md).  
  
 Si vous utilisez **\/Zc:forScope\-** dans un projet contenant déjà un fichier .pch, un avertissement est généré, **\/Zc:forScope\-** est ignoré et la compilation continue en utilisant les fichiers .pch existants. Si vous voulez qu’un nouveau fichier .pch soit généré, utilisez [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md).  
  
 Pour plus d’informations sur les problèmes de conformité dans Visual C\+\+, consultez [Comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le volet de navigation, ouvrez la page de propriétés **Propriétés de configuration**, **C\/C\+\+**, **Langage**.  
  
3.  Modifiez la propriété **Conformité forcée dans la portée d'une boucle For**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)   
 [\/Za, \/Ze \(Désactiver les extensions de langage\)](../../build/reference/za-ze-disable-language-extensions.md)