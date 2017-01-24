---
title: "Fonctions membres de flux de fichiers de sortie | Microsoft Docs"
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
helpviewer_keywords: 
  - "flux de sortie, fonctions membres"
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fonctions membres de flux de fichiers de sortie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les méthodes du flux de sortie contiennent trois types : celles qui sont équivalentes aux manipulateurs, celles qui effectuent des opérations d'écriture non formatées, et celles qui modifient d'une autre manière l'état du flux de données et n'ont aucun manipulateur ou opérateur d'insertion équivalent.  Pour des résultat mis en forme, séquentiel, vous pourriez n'utiliser que des opérateurs d'insertion et des manipulateurs.  Pour la sortie d'un accès aléatoire binaire aux disques, vous utilisez d'autres méthodes, avec ou sans les opérateurs d'insertion.  
  
## La fonction ouverte pour les flux de sortie  
 Pour utiliser un flux de sortie \([ofstream](../Topic/ofstream.md)\), vous devez associer ce flux de données avec un fichier de disque spécifique dans le constructeur ou la fonction de **ouvrir**.  Si vous utilisez la fonction de **ouvrir**, vous pouvez réutiliser le même objet de flux avec une série de fichiers.  Dans l'un et l'autre cas, les arguments décrivant le fichier sont identiques.  
  
 Lorsque vous ouvrez le fichier associé à un flux de sortie, vous avez généralement un indicateur d' **open\_mode**.  Vous pouvez combiner ces indicateurs, définis comme des énumérateurs dans la classe `ios`, avec l'opérateur OU de bit \( &#124; \).  Voir le [ios\_base::openmode](../Topic/ios_base::openmode.md) pour obtenir la liste des énumérateurs.  
  
 Trois cas actuelles du flux de sortie impliquent des options d'affichage :  
  
-   Créer un fichier.  Si le fichier existe déjà, l'ancienne version est supprimée.  
  
    ```  
    ostream ofile( "FILENAME" );  // Default is ios::out  
    ofstream ofile( "FILENAME", ios::out ); // Equivalent to above  
    ```  
  
-   Ajout d'enregistrements à un fichier existant ou création du fichier s'il n'existe pas.  
  
    ```  
    ofstream ofile( "FILENAME", ios::app );  
    ```  
  
-   Ouvrez deux fichiers, un par un, du même flux de données.  
  
    ```  
    ofstream ofile();  
    ofile.open( "FILE1", ios::in );  
    // Do some output  
    ofile.close(); // FILE1 closed  
    ofile.open( "FILE2", ios::in );  
    // Do some more output  
    ofile.close(); // FILE2 closed  
    // When ofile goes out of scope it is destroyed.  
    ```  
  
## La fonction put  
 La fonction de **put** écrit un caractère dans le flux de sortie.  Les deux instructions suivantes sont identiques par défaut, mais la deuxième est affectée par les arguments du format de flux de données :  
  
```  
cout.put( 'A' ); // Exactly one character written  
cout << 'A'; // Format arguments 'width' and 'fill' apply   
```  
  
## La fonction écrire  
 La fonction de **écrire** écrit un bloc de mémoire à un flux de sortie.  L'argument de longueur spécifie le nombre d'octets écrits.  Cet exemple crée un flux de sortie et il écrit la valeur binaire de la structure de `Date` :  
  
```  
// write_function.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
  
struct Date  
{  
   int mo, da, yr;  
};  
  
int main( )  
{  
   Date dt = { 6, 10, 92 };  
   ofstream tfile( "date.dat" , ios::binary );  
   tfile.write( (char *) &dt, sizeof dt );  
}  
```  
  
 La fonction **écrire** n'arrête pas lorsqu'elle atteint un caractère NULL, ainsi la structure de fichiers complète est écrite.  La fonction accepte deux arguments : un pointeur de `char` et un nombre de caractères à écrire.  Notez la conversion nécessaire à **char\*** avant l'adressage de l'objet de structure.  
  
## Les fonctions seekp et tellp  
 Un flux de sortie conserve un pointeur interne qui indique l'emplacement où les données doivent être écrites ensuite.  La méthode `seekp` définit le pointeur et fournit la sortie à accès aléatoire de fichier disque.  La méthode `tellp` retourne la position du fichier.  Pour obtenir des exemples qui utilisent les flux d'entrée équivalents à `seekp` et `tellp`, consultez [Les fonctions seekg et tellg](../standard-library/input-stream-member-functions.md).  
  
## La fonction fermer pour les flux de sortie  
 La méthode **fermer** ferme le fichier disque associé à un flux de sortie.  Le fichier doit être fermé pour effectuer toute la sortie de disque.  Si nécessaire, le destructeur de `ofstream` ferme le fichier pour vous, mais vous pouvez utiliser la fonction **fermer** si vous devez ouvrir un autre fichier pour le même objet de flux.  
  
 Le destructeur de flux de sortie ferme automatiquement le fichier d'un flux de données uniquement si le constructeur ou la méthode **ouvrir** a ouvert le fichier.  Si vous passez au constructeur un descripteur de fichier d'un fichier déjà ouvert ou si vous utilisez la méthode **attacher**, fermez le fichier explicitement.  
  
##  <a name="vclrferrorprocessingfunctionsanchor10"></a> Erreur de traitement des fonctions  
 Utilisez ces méthodes pour déterminer les erreurs lors de l'écriture dans un flux de données :  
  
|Fonction|Valeur de retour|  
|--------------|----------------------|  
|[mauvais](../Topic/basic_ios::bad.md)|Retourne **vrai** si une erreur est irrécupérable.|  
|[échec](../Topic/basic_ios::fail.md)|Retourne **vrai** s'il se produit une erreur irrécupérable ou un état « attendu », tel qu'une erreur de conversion, ou si le fichier est introuvable.  Le traitement peut souvent continuer après un appel à **effacer** avec l'argument zéro.|  
|[bon](../Topic/basic_ios::good.md)|Retourne **vrai** s'il n'existe aucune condition d'erreur irrécupérable \(ou autre\) et l'indicateur de fin de fichier n'est pas défini.|  
|[eof](../Topic/basic_ios::eof.md)|Retourne **vrai** sur la condition de fin du fichier.|  
|[clear](../Topic/basic_ios::clear.md)|Définit l'état d'erreur interne.  Si elle est appelée avec les arguments par défaut, elle efface tous les bits d'erreur.|  
|[rdstate](../Topic/basic_ios::rdstate.md)|Retourne l'état d'erreur courant.|  
  
 L'opérateur **\!** est surchargé pour effectuer la même fonction que la fonction **échec**.  D'où l'expression suivante :  
  
```  
if( !cout)...  
```  
  
 équivaut à :  
  
```  
if( cout.fail() )...  
```  
  
 L'opérateur **void\*\(\)** est surchargé afin d'être l'inverse de l'opérateur de **\!** ; d'où l'expression suivante :  
  
```  
if( cout)...  
```  
  
 est égal à :  
  
```  
if( !cout.fail() )...  
```  
  
 L'opérateur **void\*\(\)** n'est pas équivalent à **bon** car il ne test pas à la recherche de la fin du fichier.  
  
## Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)