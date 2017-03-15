---
title: "/WL (Activer un diagnostic de ligne) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/wl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/WL (option du compilateur C++)"
  - "WL (option du compilateur C++)"
  - "-WL (option du compilateur C++)"
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /WL (Activer un diagnostic de ligne)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute des informations supplémentaires à un message d'erreur ou d'avertissement.  
  
## Syntaxe  
  
```  
/WL  
```  
  
## Notes  
 Les messages d'erreur et d'avertissement émis par le compilateur C\+\+ peuvent être suivis d'informations supplémentaires qui apparaissent, par défaut, sur une nouvelle ligne.  Lorsque vous compilez à partir de la ligne de commande, la ligne supplémentaire d'informations peut être ajoutée au message d'erreur ou d'avertissement.  Cela peut être utile si vous capturez votre sortie de génération dans un fichier journal puis que vous examinez ce journal pour rechercher toutes les erreurs et tous les avertissements.  Un point\-virgule sépare le message d'erreur ou d'avertissement de la ligne supplémentaire.  
  
 Certains messages d'erreur et d'avertissement n'ont pas de ligne supplémentaire d'informations.  Le code suivant génère une erreur qui possède une ligne supplémentaire d'informations ; il vous permet de voir le résultat obtenu lors de l'utilisation de l'option **\/WL**.  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)