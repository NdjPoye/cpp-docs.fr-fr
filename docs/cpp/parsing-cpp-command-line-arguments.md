---
title: "Analyse des arguments de ligne de commande C++ | Microsoft Docs"
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
  - "guillemets, les arguments de ligne de commande"
  - "guillemets doubles"
  - "l’analyse de ligne de commande"
  - "analyse des arguments de ligne de commande"
  - "code de démarrage, l’analyse des arguments de ligne de commande"
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Analyse des arguments de ligne de commande C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Code de démarrage Microsoft C/C++ utilise les règles suivantes pour interpréter les arguments spécifiés sur la ligne de commande du système d’exploitation :  
  
-   Les arguments sont délimités par un espace blanc, qui peut être un espace ou une tabulation.  
  
-   L’accent circonflexe (^) n’est pas reconnu comme un caractère d’échappement ou du délimiteur. Le caractère est géré complètement par l’Analyseur de ligne de commande du système d’exploitation avant d’être passé à le `argv` tableau dans le programme.  
  
-   Une chaîne placée entre guillemets doubles («*chaîne*») est interprétée comme un argument unique, quel que soit le contenu dans un espace blanc. Une chaîne entre guillemets peut être incorporée dans un argument.  
  
-   Un guillemet double précédé d’une barre oblique inverse (\\») est interprétée comme un caractère guillemet double littéral («).  
  
-   Les barres obliques inverses sont interprétées littéralement, sauf si elles précèdent immédiatement un guillemet double.  
  
-   Si un nombre pair de barres obliques inverses est suivi d’un guillemet double, une barre oblique inverse est placée dans le `argv` tableau pour chaque paire de barres obliques inverses et le guillemet double est interprété comme un délimiteur de chaîne.  
  
-   Si un nombre impair de barres obliques inverses est suivi d’un guillemet double, une barre oblique inverse est placée dans le `argv` tableau pour chaque paire de barres obliques inverses et le guillemet double est « échappé » par la barre oblique inverse restante, provoquant un guillemet double littéral (") est placé dans `argv`.  
  
## <a name="example"></a>Exemple  
 Le programme suivant montre les arguments de la ligne de commande sont passés :  
  
```  
// command_line_arguments.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main( int argc,      // Number of strings in array argv  
          char *argv[],   // Array of command-line argument strings  
          char *envp[] )  // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    cout << "\nCommand-line arguments:\n";  
    for( count = 0; count < argc; count++ )  
         cout << "  argv[" << count << "]   "  
                << argv[count] << "\n";  
}  
```  
  
 Le tableau suivant présente l’exemple d’entrée et de sortie attendue, démontrant les règles dans la liste précédente.  
  
### <a name="results-of-parsing-command-lines"></a>Résultats d’analyse de ligne de commande  
  
|Entrée sur la ligne de commande|argv[1]|argv [2]|argv [3]|  
|-------------------------|---------------|---------------|---------------|  
|`"abc" d e`|`abc`|`d`|`e`|  
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
## <a name="end-microsoft-specific"></a>FIN de la section spécifique à Microsoft  
  
## <a name="see-also"></a>Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)