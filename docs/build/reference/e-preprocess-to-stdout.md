---
title: "/E (Pr&#233;traiter dans stdout) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/E (option du compilateur C++)"
  - "-E (option du compilateur C++)"
  - "sortie du préprocesseur"
  - "sortie du préprocesseur, copier dans stdout"
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /E (Pr&#233;traiter dans stdout)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prétraite des fichiers source C et C\+\+, puis copie les fichiers prétraités vers le périphérique de sortie standard.  
  
## Syntaxe  
  
```  
/E  
```  
  
## Notes  
 Au cours de cette opération, toutes les directives du préprocesseur sont exécutées, les expansions de macros sont effectuées et les commentaires sont supprimés.  Pour conserver les commentaires dans la sortie prétraitée, utilisez également l'option du compilateur [\/C \(Conserver les commentaires pendant le prétraitement\)](../../build/reference/c-preserve-comments-during-preprocessing.md).  
  
 **\/E** ajoute des directives `#line` dans la sortie, au début et à la fin de chaque fichier inclus et autour des lignes supprimées par les directives du préprocesseur pour une compilation conditionnelle.  Ces directives renumérotent les lignes du fichier prétraité.  Résultat : les erreurs générées pendant les phases ultérieures du traitement désignent les numéros de ligne du fichier source d'origine et non pas les lignes du fichier prétraité.  
  
 L'option **\/E** supprime la compilation.  Vous devez soumettre de nouveau le fichier prétraité en vue de sa compilation.  **\/E** supprime également les fichiers de sortie des options **\/FA**, **\/Fa** et **\/Fm**.  Pour plus d’informations, consultez [\/FA, \/Fa \(Fichier listing\)](../../build/reference/fa-fa-listing-file.md) et [\/Fm \(Nom de fichier de mappage\)](../../build/reference/fm-name-mapfile.md).  
  
 Pour supprimer les directives `#line`, utilisez plutôt l'option [\/EP \(Prétraiter dans stdout sans directive \#line\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).  
  
 Pour envoyer la sortie prétraitée dans un fichier et pas dans `stdout`, utilisez l'option [\/P \(Prétraiter jusqu'à un fichier\)](../../build/reference/p-preprocess-to-a-file.md).  
  
 Pour supprimer les directives `#line` et envoyer la sortie prétraitée dans un fichier, utilisez **\/P** et **\/EP** ensemble.  
  
 Vous ne pouvez pas utiliser des en\-têtes précompilés avec l'option **\/E**.  
  
 Notez que lors d'un prétraitement vers un fichier distinct, les espaces ne sont pas émis après les jetons.  Cela peut donner lieu à un programme non conforme ou générer des effets secondaires inattendus.  Le programme suivant se compile correctement :  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 Cependant, si vous compilez avec :  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 `int main` dans test2.cpp donnera incorrectement `intmain`.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## Exemple  
 La ligne de commande suivante prétraite `ADD.C`, conserve les commentaires, ajoute les directives `#line` et affiche le résultat sur le périphérique de sortie standard :  
  
```  
CL /E /C ADD.C  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)