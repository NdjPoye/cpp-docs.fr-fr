---
title: "Instanciation explicite | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modèles, instanciation"
  - "instanciation explicite"
  - "instanciation, explicite"
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Instanciation explicite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'instanciation explicite pour créer une instanciation d'une classe ou fonction modélisée sans réellement l'utiliser dans votre code.  Puisque c'est utile lorsque vous créez des fichiers bibliothèque \(.lib\) qui utilisent des modèles pour la distribution, les définitions de modèle non instanciées ne sont pas stockées dans des fichiers objet \(.obj\).  
  
 Ce code instancie explicitement `MyStack` pour les variables `int` et six éléments :  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 Cette instruction crée une instanciation de `MyStack` sans réserver d'espace de stockage pour un objet.  Le code est généré pour tous les membres.  
  
 La ligne suivante instancie explicitement uniquement la fonction membre du constructeur :  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 Vous pouvez explicitement instancier des modèles de fonction à l'aide d'un argument de type spécifique pour les redéclarer, comme indiqué dans l'exemple [Instanciation du modèle de fonction](../cpp/function-template-instantiation.md).  
  
 Utilisez le mot clé `extern` pour empêcher l'instanciation automatique des membres.  Par exemple :  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 De même, vous pouvez marquer des membres spécifiques comme étant externes et non instanciés :  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 Utilisez le mot clé `extern` pour empêcher le compilateur de générer le même code d'instanciation dans plus d'un module objet.  Vous devez instancier la fonction de modèle en utilisant les paramètres de modèle explicites spécifiés dans au moins un module lié si la fonction est appelée, ou vous obtiendrez une erreur de l'éditeur de liens lorsque le programme est généré.  
  
> [!NOTE]
>  Le mot clé `extern` de la spécialisation s'applique uniquement aux fonctions membres définies en dehors du corps de la classe.  Les fonctions définies dans la déclaration de classe sont considérées comme des fonctions incluses et sont toujours instanciées.  
  
## Voir aussi  
 [Modèles de fonctions](../cpp/function-templates.md)