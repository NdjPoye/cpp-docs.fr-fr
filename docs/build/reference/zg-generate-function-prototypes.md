---
title: "/Zg (G&#233;n&#233;rer les prototypes de fonction) | Microsoft Docs"
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
  - "/zg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zg (option du compilateur C++)"
  - "prototypes de fonctions, générer des prototypes de fonction (option du compilateur)"
  - "générer des prototypes de fonction (option du compilateur)"
  - "Zg (option du compilateur C++)"
  - "-Zg (option du compilateur C++)"
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zg (G&#233;n&#233;rer les prototypes de fonction)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprimé. Crée un prototype de fonction pour chaque fonction définie dans le fichier source, mais ne compile pas le fichier source.  
  
## Syntaxe  
  
```  
/Zg  
```  
  
## Notes  
 Cette option du compilateur n’est plus disponible. Elle a été supprimée dans Visual C\+\+ 2015. Cette page est destinée aux utilisateurs de versions antérieures de Visual C\+\+.  
  
 Le prototype de fonction comprend le type de retour de fonction et une liste de types d’arguments. La liste de types d’arguments est créée à partir des types des paramètres formels de la fonction. Les prototypes de fonctions déjà présents dans le fichier source sont ignorés.  
  
 La liste des prototypes est écrite dans la sortie standard. Cette liste peut vous aider à vérifier que les arguments réels et les paramètres formels d’une fonction sont compatibles. Vous pouvez enregistrer la liste en redirigeant la sortie standard vers un fichier. Vous pouvez ensuite utiliser **\#include** pour ajouter la liste des prototypes de fonctions dans votre fichier source. Cela permet au compilateur d’effectuer une vérification des types d’arguments.  
  
 Si vous utilisez l’option **\/Zg** et que votre programme contient des paramètres formels avec les types struct, enum ou union \(ou qu’il contient des pointeurs vers ces types\), la déclaration de chaque type struct, enum ou union doit être accompagnée d’une balise \(le nom\). Dans l’exemple suivant, le nom de la balise est `MyStruct`.  
  
```  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 **\/Zg** est déconseillé. Il est prévu que le compilateur Visual C\+\+ ne prenne plus en charge le code ancien de style C. Pour plus d’informations, consultez [Options du compilateur déconseillées et supprimées dans Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option de compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)