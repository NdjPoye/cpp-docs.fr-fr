---
title: "commentaire (C/C++) | Microsoft Docs"
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
  - "vc-pragma.comment"
  - "comment_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "annotations (C++)"
  - "comment (pragma)"
  - "commentaires (C++), fichiers compilés"
  - "pragmas, commentaire"
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# commentaire (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Place un enregistrement de commentaires dans un fichier objet ou un fichier exécutable.  
  
## Syntaxe  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## Notes  
 *comment\-type* est l'un des identificateurs prédéfinis, décrit ci\-dessous, qui spécifie le type d'enregistrement de commentaires.  L'élément `commentstring` facultatif est un littéral de chaîne qui fournit des informations supplémentaires pour certains types de commentaires.  Comme `commentstring` est un littéral de chaîne, il respecte toutes les règles des littéraux de chaîne concernant les caractères d'échappement, les guillemets incorporés \(**"**\) et la concaténation.  
  
 **compiler**  
 Place le nom et le numéro de version du compilateur dans le fichier objet.  Cet enregistrement de commentaires est ignoré par l'Éditeur de liens.  Si vous fournissez un paramètre `commentstring` pour ce type d'enregistrement, le compilateur génère un avertissement.  
  
 **exestr**  
 Place `commentstring` dans le fichier objet.  Au moment d'effectuer le lien, cette chaîne est placée dans le fichier exécutable.  La chaîne n'est pas chargée en mémoire lorsque le fichier exécutable est chargé. Toutefois, elle peut être détectée à l'aide d'un programme qui recherche les chaînes imprimables dans les fichiers.  Ce type d'enregistrement de commentaires peut être utilisé par exemple pour incorporer un numéro de version ou des informations similaires dans un fichier exécutable.  
  
 Le mot clé `exestr` est déconseillé et sera supprimé dans une version ultérieure. L'Éditeur de liens ne traite pas l'enregistrement de commentaires.  
  
 **lib**  
 Place un enregistrement de recherche de bibliothèque dans le fichier objet.  Ce type de commentaires doit être accompagné d'un paramètre `commentstring` contenant le nom \(et éventuellement le chemin d'accès\) de la bibliothèque dans laquelle vous souhaitez que l'Éditeur de liens effectue une recherche.  Le nom de la bibliothèque suit les enregistrements de recherche de bibliothèque par défaut dans le fichier objet. L'Éditeur de liens recherche cette bibliothèque comme si vous l'aviez nommée dans la ligne de commande, à condition que la bibliothèque ne soit pas spécifiée avec [\/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md).  Vous pouvez placer plusieurs enregistrements de recherche de bibliothèque dans le même fichier source. Les enregistrements figurent dans le fichier objet dans l'ordre où ils sont rencontrés dans le fichier source.  
  
 Si l'ordre de la bibliothèque par défaut et d'une bibliothèque ajoutée est important, la compilation avec le commutateur [\/Zl](../build/reference/zl-omit-default-library-name.md) empêchera le placement du nom de la bibliothèque par défaut dans le module objet.  Un deuxième pragma comment peut alors être utilisé pour insérer le nom de la bibliothèque par défaut après la bibliothèque ajoutée.  Les bibliothèques répertoriées avec ces pragmas figureront dans le module objet, dans l'ordre où elles sont trouvées dans le code source.  
  
 **linker**  
 Place une [option d'Éditeur de liens](../build/reference/linker-options.md) dans le fichier objet.  Vous pouvez utiliser ce type\-commentaire pour spécifier une option d'éditeur de liens au lieu de la passer à la ligne de commande ou de la spécifier dans l'environnement de développement.  Par exemple, vous pouvez spécifier l'option \/include pour forcer l'inclusion d'un symbole :  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 Seules les options d'éditeur de liens suivantes \(*comment\-type*\) peuvent être passées à l'identificateur d'éditeur de liens :  
  
-   [\/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [\/EXPORT](../build/reference/export-exports-a-function.md)  
  
-   [\/INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [\/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [\/MERGE](../build/reference/merge-combine-sections.md)  
  
-   [\/SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **utilisateur**  
 Place un commentaire général dans le fichier objet.  Le paramètre `commentstring` contient le texte du commentaire.  Cet enregistrement de commentaires est ignoré par l'Éditeur de liens.  
  
 Le pragma ci\-dessous indique à l'Éditeur de liens de rechercher la bibliothèque EMAPI.LIB en effectuant la liaison.  L'Éditeur de liens commence par rechercher dans le répertoire de travail actuel, puis dans le chemin d'accès spécifié dans la variable d'environnement LIB.  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 Le pragma ci\-dessous indique au compilateur de placer le nom et le numéro de version du compilateur dans le fichier objet :  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  Pour les commentaires qui acceptent un paramètre `commentstring`, vous pouvez utiliser une macro dans tous les emplacements où vous utiliseriez un littéral de chaîne, à condition que la macro se développe en un littéral de chaîne.  Vous pouvez également concaténer toute combinaison de littéraux de chaîne et de macros qui se développent en littéraux de chaîne.  Par exemple, l'instruction suivante est acceptable :  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)