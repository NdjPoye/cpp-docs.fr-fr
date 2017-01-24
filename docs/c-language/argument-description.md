---
title: "Description des arguments | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "argc (argument)"
  - "arguments (C++), pour fonction main"
  - "argv (argument)"
  - "envp (argument)"
  - "main (fonction), syntaxe"
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Description des arguments
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le paramètre `argc` dans les fonctions **main** et **wmain** est un entier spécifiant le nombre d'arguments passés au programme depuis la ligne de commande.  Le nom du programme étant considéré comme un argument, la valeur `argc` est d'au moins un.  
  
## Remarques  
 Le paramètre `argv` est un tableau de pointeurs vers des chaînes terminées par le caractère NULL qui représente les arguments de programme.  Chaque élément du tableau pointe vers une représentation sous forme de chaîne d'un argument passé à **main** \(ou **wmain**\). \(Pour plus d'informations sur les tableaux, consultez [Déclarations de tableau](../c-language/array-declarations.md).\) Le paramètre `argv` peut être déclaré soit comme tableau de pointeurs en type `char` \(`char *argv[]`\) soit comme pointeur vers des pointeurs en type `char` \(`char **argv`\).  Pour **wmain**, le paramètre `argv` peut être déclaré soit comme tableau de pointeurs en type `wchar_t` \(`wchar_t *argv[]`\) soit comme pointeur vers des pointeurs en type `wchar_t` \(`wchar_t **argv`\).  
  
 Par convention, `argv`**\[0\]** est la commande avec laquelle le programme est appelé.  Toutefois, il est possible de générer un processus utilisant [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425) et si vous utilisez à la fois le premier et le deuxième argument \(`lpApplicationName` et `lpCommandLine`\), `argv`**\[0\]** peut ne pas être le nom exécutable. Utilisez [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197) pour récupérer le nom exécutable.  
  
 Le dernier pointeur \(`argv[argc]`\) est **NULL**. \(Consultez [getenv](../c-runtime-library/reference/getenv-wgetenv.md) dans la *Référence de la bibliothèque runtime* pour une connaître autre méthode pour obtenir des informations de variable d'environnement.\)  
  
 **Section spécifique à Microsoft**  
  
 Le paramètre `envp` est un pointeur vers un tableau de chaînes terminées par le caractère NULL qui représentent les valeurs définies dans les variables d'environnement de l'utilisateur.  Le paramètre `envp` peut être déclaré comme tableau de pointeurs en type `char` \(`char *envp[]`\) ou comme pointeur vers des pointeurs en type `char` \(`char **envp`\).  Dans une fonction **wmain**, le paramètre `envp` peut être déclaré comme tableau de pointeurs vers `wchar_t` \(`wchar_t *envp[]`\) ou comme pointeur vers des pointeurs en `wchar_t` \(`wchar_t **envp`\).  La fin du tableau est affichée par un pointeur **NULL** \*.  Notez que le bloc environnement passé à **main** ou **wmain** est une copie « figée » de l'environnement actuel.  Si vous modifiez ultérieurement l'environnement via un appel à \_**putenv** ou `_wputenv`, l'environnement actuel \(tel que retourné par `getenv`\/`_wgetenv` et les variables `_environ` ou `_wenviron`\) est modifié, mais pas le bloc dirigé vers `envp`.  Le paramètre `envp` est compatible ANSI en C, mais pas en C\+\+.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Fonction main et exécution du programme](../c-language/main-function-and-program-execution.md)