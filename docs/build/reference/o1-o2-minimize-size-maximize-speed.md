---
title: "/O1, /O2 (R&#233;duire la taille, augmenter la vitesse) | Microsoft Docs"
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
  - "/o2"
  - "/o1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/O1 (option du compilateur C++)"
  - "/O2 (option du compilateur C++)"
  - "code rapide"
  - "augmenter la vitesse (option du compilateur C++)"
  - "réduire la taille (option du compilateur C++)"
  - "O1 (option du compilateur C++)"
  - "-O1 (option du compilateur C++)"
  - "O2 (option du compilateur C++)"
  - "-O2 (option du compilateur C++)"
  - "code compact"
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /O1, /O2 (R&#233;duire la taille, augmenter la vitesse)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sélectionne un jeu prédéfini d'options qui affectent la taille et la vitesse des fichiers.  
  
## Syntaxe  
  
```  
/O1  
/O2  
```  
  
## Notes  
 Le tableau suivant décrit **\/O1** et **\/O2**.  
  
|Option|Équivalent à|Commentaire|  
|------------|------------------|-----------------|  
|**\/O1** \(Réduire la taille\)|**\/Og \/Os \/Oy \/Ob2 \/Gs \/GF \/Gy**|Crée le code le plus compact possible dans la majorité des cas.|  
|**\/O2** \(Augmenter la vitesse\)|**\/Og \/Oi \/Ot \/Oy \/Ob2 \/Gs \/GF \/Gy**|Crée le code le plus rapide dans la plupart des cas. \(paramètre par défaut pour les versions release\)|  
  
 **\/O1** et **\/O2** activent également l'optimisation des valeurs de retour nommées, qui élimine le constructeur de copie et le destructeur d'une valeur de retour basée sur la pile.  Prenons l'exemple suivant.  La fonction `Test` ne crée pas le constructeur de copie ou le destructeur.  Ajoutez des instructions de sortie au constructeur, au destructeur et au constructeur de copie afin de voir l'effet de l'optimisation des valeurs de retour nommées lors de l'exécution du programme.  Pour plus d'informations, consultez [Optimisation nommée de valeur de retour dans Visual C\+\+ 2005](http://go.microsoft.com/fwlink/?linkid=131571).  
  
```  
// O1_O2_NRVO.cpp  
// compile with: /O1  
struct A {  
   A() {}  
   ~A() {}  
   A(const A& aa) {}  
};  
  
A Test() {  
   A a;  
   return a;  
}  
int main() {  
   A aa;  
   aa = Test();  
}  
```  
  
 **Section spécifique à x86**  
  
 Ces options impliquent l'utilisation de l'option [\/Oy](../../build/reference/oy-frame-pointer-omission.md) \(Omission du pointeur frame\).  
  
 **FIN Spécifique x86**  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Optimisation**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md)