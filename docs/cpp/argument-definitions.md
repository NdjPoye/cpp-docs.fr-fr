---
title: "D&#233;finitions d&#39;arguments | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "argc (argument)"
  - "arguments (C++), pour fonction main"
  - "argv (argument)"
  - "envp (argument)"
  - "main (fonction), arguments"
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finitions d&#39;arguments
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les arguments dans le prototype  
  
```  
  
int main( int argc[ , char *argv[ ] [, char *envp[ ] ] ] ); int wmain( int argc[ , wchar_t *argv[ ] [, wchar_t *envp[ ] ] ] );  
```  
  
 permettent d'analyser facilement les arguments sur la ligne de commande et, éventuellement, d'accéder aux variables d'environnement.  Les définitions d'argument sont les suivantes :  
  
 `argc`  
 Entier qui contient le nombre d'arguments qui se suivent dans `argv`.  Le paramètre `argc` est toujours supérieur ou égal à 1.  
  
 `argv`  
 Tableau de chaînes terminées par le caractère NULL qui représentent les arguments de ligne de commande entrés par l'utilisateur du programme.  Par convention, `argv`**\[0\]** est la commande avec laquelle le programme est appelé, `argv`**\[1\]** est le premier argument de ligne de commande, et ainsi de suite, jusqu'à `argv`**\[**`argc`**\]**, qui est toujours **NULL**.  Consultez [Personnalisation du traitement de la ligne de commande](../cpp/customizing-cpp-command-line-processing.md) pour plus d'informations sur la suppression du traitement de la ligne de commande.  
  
 Le premier argument de ligne de commande est toujours `argv`**\[1\]** et le dernier `argv`**\[**`argc` – 1**\]**.  
  
> [!NOTE]
>  Par convention, `argv`**\[0\]** est la commande avec laquelle le programme est appelé.  Toutefois, il est possible de générer un processus à l'aide de [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197) et si vous utilisez le premier et le deuxième argument \(`lpApplicationName` et `lpCommandLine`\), `argv`**\[0\]** peut ne pas être le nom de l'exécutable. Utilisez [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197) pour récupérer le nom de l'exécutable, ainsi que son chemin d'accès complet.  
  
## Section spécifique à Microsoft  
 `envp`  
 Le tableau `envp`, qui est une extension courante dans de nombreux systèmes Unix, est utilisé dans Microsoft C\+\+.  Il s'agit d'un tableau de chaînes représentant les variables définies dans l'environnement de l'utilisateur.  Ce tableau se termine par une entrée **NULL**.  Il peut être déclaré comme tableau de pointeurs vers **char \(char** \*envp\[ \]**\)** ou comme pointeur vers pointeurs vers **char \(char** \*\* envp**\)**.  Si votre programme utilise **wmain** au lieu de **main**, utilisez le type de données `wchar_t` au lieu de `char`.  Le bloc environnement passé à **main** et **wmain** est une copie « figée » de l'environnement actuel.  Si vous modifiez ultérieurement l'environnement via un appel à **putenv** ou `_wputenv`, l'environnement actuel \(tel que retourné par `getenv`\/`_wgetenv` et la variable `_environ`\/ `_wenviron`\) est modifié, mais pas le bloc dirigé vers envp.  Consultez [Personnalisation du traitement de la ligne de commande](../cpp/customizing-cpp-command-line-processing.md) pour plus d'informations sur la suppression du traitement de l'environnement.  Cet argument est compatible ANSI en C, mais pas en C\+\+.  
  
## FIN de la section spécifique à Microsoft  
  
## Exemple  
 L'exemple suivant illustre l'utilisation des événements `argc`, `argv` et `envp` avec **main** :  
  
```  
// argument_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
int main( int argc, char *argv[], char *envp[] ) {  
    int iNumberLines = 0;    // Default is no line numbers.  
  
    // If /n is passed to the .exe, display numbered listing  
    // of environment variables.  
  
    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )  
         iNumberLines = 1;  
  
    // Walk through list of strings until a NULL is encountered.  
    for( int i = 0; envp[i] != NULL; ++i ) {  
        if( iNumberLines )  
            cout << i << ": " << envp[i] << "\n";  
    }  
}  
```  
  
## Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)