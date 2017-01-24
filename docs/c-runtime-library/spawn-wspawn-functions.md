---
title: "_spawn, _wspawn, fonctions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_spawn"
  - "_tspawnlp"
  - "_tspawnlpe"
  - "_tspawnve"
  - "_tspawnvp"
  - "_tspawnvpe"
  - "_tspawnl"
  - "spawn"
  - "_tspawnv"
  - "_tspawnle"
  - "wspawn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tspawnve, fonction"
  - "_spawn, fonctions"
  - "_tspawnlpe, fonction"
  - "tspawnvpe, fonction"
  - "processus, création"
  - "tspawnve, fonction"
  - "_tspawnvp, fonction"
  - "spawn, fonctions"
  - "tspawnl, fonction"
  - "tspawnlp, fonction"
  - "_tspawnvpe, fonction"
  - "_tspawnl, fonction"
  - "tspawnvp, fonction"
  - "tspawnv, fonction"
  - "processus, exécuter un nouveau"
  - "_tspawnv, fonction"
  - "tspawnle, fonction"
  - "processus, création"
  - "_tspawnlp, fonction"
  - "tspawnlpe, fonction"
  - "_tspawnle, fonction"
ms.assetid: bb47c703-5216-4e09-8023-8cf25bbf2cf9
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _spawn, _wspawn, fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chacune des fonctions `_spawn` crée et exécute un nouveau processus :  
  
|||  
|-|-|  
|[\_spawnl, \_wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[\_spawnv, \_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|  
|[\_spawnle, \_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[\_spawnve, \_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|  
|[\_spawnlp, \_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[\_spawnvp, \_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|  
|[\_spawnlpe, \_wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[\_spawnvpe, \_wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|  
  
 Les lettres à la fin du nom de la fonction détermine la variation.  
  
 `e`  
 `envp`, un tableau de pointeurs aux paramètres d'environnement, est passé au nouveau processus.  
  
 `l`  
 Les arguments de ligne de commande sont passés individuellement à la fonction d'`_spawn`.  Le suffixe est généralement employé lorsqu'un nombre quelconque de paramètres d'un nouveau processus est connu d'avance.  
  
 `p`  
 la variable d'environnement`PATH` est utilisée pour rechercher le fichier à exécuter.  
  
 `v`  
 `argv`, un tableau de pointeurs vers des arguments de ligne de commande, est passé à `_spawn`.  Le suffixe est généralement employée lorsqu'un nombre quelconque de paramètres d'un nouveau processus est variable.  
  
## Notes  
 Les fonctions`_spawn` s'exécutent et chacune créee et exécute un nouveau processus.  Les fonctions reconnaissent automatiquement des arguments de chaîne de caractères multi\-octets comme appropriés, en identifiant des séquences de caractères multi\-octets d'après la page de codes multioctets en cours d'utilisation.  Les fonctions `_wspawn` sont des versions caractères larges des fonctions `_spawn` ; ils ne gèrent pas les chaînes de caractères multi\-octets.  Sinon, les fonctions `_wspawn` se comportent de la même manière que leurs équivalents `_spawn`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tspawnl`|`_spawnl`|`_spawnl`|`_wspawnl`|  
|`_tspawnle`|`_spawnle`|`_spawnle`|`_wspawnle`|  
|`_tspawnlp`|`_spawnlp`|`_spawnlp`|`_wspawnlp`|  
|`_tspawnlpe`|`_spawnlpe`|`_spawnlpe`|`_wspawnlpe`|  
|`_tspawnv`|`_spawnv`|`_spawnv`|`_wspawnv`|  
|`_tspawnve`|`_spawnve`|`_spawnve`|`_wspawnve`|  
|`_tspawnvp`|`_spawnvp`|`_spawnvp`|`_wspawnvp`|  
|`_tspawnvpe`|`_spawnvpe`|`_spawnvpe`|`_wspawnvpe`|  
  
 Une quantité de mémoire suffisante doit être disponible pour charger et exécuter le nouveau processus.  L'argument `mode` détermine l'action entreprise par le processus appelant avant et pendant `_spawn`.  Les valeurs suivantes pour `mode` sont définies dans Process.h :  
  
 `_P_OVERLAY`  
 Recouvre un processus appellant par un nouveau processus, détruisant le processus appelant \(le même effet que des appels à`_exec` \).  
  
 `_P_WAIT`  
 Interrompt un thread appelant jusqu'à ce que l'exécution du nouveau processus soit terminée `_spawn`\(synchrone\).  
  
 `_P_NOWAIT` ou `_P_NOWAITO`  
 Continue d'exécuter un processus appelant en même temps que le nouveau processus \( `_spawn`asynchrones\).  
  
 `_P_DETACH`  
 Continue d'exécuter le processus appelant ; le nouveau processus est exécuté en arrière\-plan sans accès à la console ou au clavier.  Les appels à `_cwait` sur le nouveau processus échouent `_spawn`\(asynchrone\).  
  
 L'argument `cmdname` spécifie le fichier exécuté en tant que nouveau processus et peut spécifier un chemin d'accès complet \(de la racine\), un chemin d'accès \(partiel du répertoire de travail actuel\), ou uniquement un nom de fichier.  Si `cmdname` ne porte pas l'extension de nom de fichier ou ne se termine pas par un point \(.\), la fonction `_spawn` tente d'abord l'extension de nom de fichier .com et l'extension de nom de fichier .exe, l'extension de nom de fichier .bat, et enfin l'extension de nom de fichier .cmd.  
  
 Si `cmdname` a une extension de nom de fichier, seule cette extension est utilisée.  Si `cmdname` se termine par un point, la fonction cherche le`_spawn` pour `cmdname` sans l'extension de nom de fichier.  `_spawnlp`, `_spawnlpe`, `_spawnvp`, et cherche  `_spawnvpe` pour `cmdname` \(à l'aide des mêmes procédures\) dans les répertoires spécifiés par la variable d'environnement `PATH`.  
  
 Si `cmdname` contient un spécificateur de lecteur ou des barres obliques \(autrement dit, si c'est un chemin d'accès relatif\), l'appel à`_spawn` recherche uniquement le fichier spécifié ; le chemin d'accès n'est pas recherché.  
  
 Dans le passé, certaines de ces fonctions ont assigné à `errno` la valeur zéro en cas de réussite ; le comportement actuel est de laisser `errno` intacte en cas de réussite, comme spécifié dans standard du language C.  Si vous devez émuler le comportement antérieur, définissez `errno` à zéro juste avant l'appel de ces fonctions.  
  
> [!NOTE]
>  Pour garantir l'initialisation appropriée et l'arrêt de chevauchement, n'utilisez pas la fonction `setjmp` ou la fonction `longjmp` pour entrer ou quitter une routine de superposition.  
  
## Arguments pour le processus engendré  
 Pour passer les arguments de nouveau processus, donnez un ou plusieurs pointeurs en chaînes de caractères comme arguments dans l'appel à`_spawn`.  Ces chaînes de caractères forment la liste d'arguments pour le processus engendré.  La taille combinée des chaînes qui forment la liste d'arguments pour le nouveau processus ne doit pas dépasser 1024 octets.  Le caractère null de fin \("\\0 "\) pour chaque chaîne n'est pas inclus dans le décompte, mais les espaces \(insérés automatiquement pour séparer les paramètres\) sont inclus.  
  
> [!NOTE]
>  Les espaces incorporés dans les chaînes peuvent provoquer un comportement inattendu ; par exemple, en passant `_spawn` la chaîne `"hi there"` donnera un résultat le nouveau processus en obtenant deux arguments, `"hi"` et `"there"`.  Si l'objectif était d'exécuter le nouveau processus ouvrir un fichier nommé « coucou », fera échouer le processus.  Évitez ceci en plaçant la chaîne suivante entre guillemets : `"\"hi there\""`.  
  
> [!IMPORTANT]
>  Ne passez pas une entrée d'utilisateur à `_spawn` sans activer explicitement son contenu.  `_spawn` entraîne un appel à [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425) donc gardez à l'esprit que les noms de chemin non qualifiés peuvent entraîner des failles de sécurité.  
  
 Vous pouvez passer des pointeurs d'arguments comme arguments différents \(dans `_spawnl`, `_spawnle`, `_spawnlp`, et `_spawnlpe`\) ou en tant que tableau de pointeurs \(dans `_spawnv`, `_spawnve`, `_spawnvp`, et `_spawnvpe`\).  Vous devez transmettre au moins un argument, `arg0` ou `argv`\[0\], au processus engendré.  Par convention, cet argument correspond au nom du programme comme vous le taperiez sur la ligne de commande.  Une valeur différente ne produit pas une erreur.  
  
 `_spawnl`, `_spawnle`, `_spawnlp`, et les appels à`_spawnlpe` sont généralement utilisés dans les cas où le nombre d'arguments est connu à l'avance.  L'argument `arg0` est généralement un pointeur vers `cmdname`.  Les arguments `arg1` à `argn` sont des pointeurs vers des chaînes de caractères qui forment la nouvelle liste d'arguments.  Après `argn`, il doit exister un pointeur `NULL` pour marquer la fin de la liste des arguments.  
  
 `_spawnv`, `_spawnve`, `_spawnvp`, et les appels à`_spawnvpe` sont utiles lorsqu'il y a un nombre variable d'arguments dans le processus.  Les pointeurs vers des paramètres sont passés comme un tableau, `argv`*.* L'argument `argv`\[0\] est généralement un pointeur vers un chemin d'accès en mode réel ou le nom du programme en mode protégé, et `argv`\[1\] à `argv`\[`n`\] sont des pointeurs vers les chaînes de caractères qui forment la nouvelle liste d'arguments.  L'argument `argv`\[`n` \+1\] doit être un pointeur `NULL` pour marquer la fin de la liste d'arguments.  
  
## Environnement du processus engendré  
 Les fichiers ouverts lorsqu'un appel à `_spawn` est effectué restent ouverts dans le nouveau processus.  Dans `_spawnl`, `_spawnlp`, `_spawnv`, et les appels à`_spawnvp`, le nouveau processus hérite de l'environnement du processus appelant.  Vous pouvez utiliser `_spawnle`, `_spawnlpe`, `_spawnve`, et les appelsà`_spawnvpe` pour modifier l'environnement du nouveau processus en passant la liste des paramètres d'environnement par l'argument `envp`.  `envp` est un tableau de pointeurs de caractère, dont chaque élément \(excepté le dernier\) pointe vers une chaîne terminée par le caractère NULL définissant une variable d'environnement.  Une telle chaîne a généralement la forme `NAME`\=`value` où `NAME` est le nom d'une variable d'environnement et `value` est la valeur de chaîne à laquelle cette variable est définie. \(Notez que `value` n'est pas placé entre guillemets.\) Le dernier élément du tableau de `envp` doit être `NULL`.  Lorsque `envp` lui\-même est `NULL`, le nouveau processus hérite des paramètres d'environnement du processus appelant.  
  
 Les fonctions `_spawn` peuvent passer toutes les informations sur les fichiers ouverts, y compris le type de mode de traduction, au nouveau processus.  Ces informations sont transmises en mode réel à l'entrée `C_FILE_INFO` dans l'environnement.  Le Code de démarrage traite généralement cette entrée et la supprime ensuite de l'environnement.  Toutefois, si une fonction `_spawn` génère un processus dans un autre language que le C, cette entrée reste dans l'environnement.  Imprimant l'environnement indique les caractères graphiques dans la chaîne de définition de cette entrée car les informations d'environnement sont transmises sous forme binaire en mode réel.  Il ne doit avoir aucun effet sur les opérations normales.  En mode protégé, les informations d'environnement sont transmises sous forme de texte et donc ne contiennent pas de caractère graphique.  
  
 Vous devez explicitement faire le ménage \(en utilisant `fflush` ou `_flushall`\) ou fermer tout flux avant l'appel de fonction `_spawn`.  
  
 Les nouveaux processus créés par des appels aux routines `_spawn` ne conservent pas les précédents paramètres de signal.  Par contre, les processus engendré reinitialise le signal à sa valeur par défaut.  
  
## Redirige la sortie  
 Si vous appelez `_spawn` d'une DLL ou d'une application graphique et que vous voulez rediriger la sortie à un canal, vous avez deux options :  
  
-   Utilisez l'API Win32 pour créer un canal, puis appelez [AllocConsole](http://msdn.microsoft.com/library/windows/desktop/ms681944), qui définit les valeurs de gestion dans la structure de démarrage, et appelez [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425).  
  
-   Appelez [\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md) ce qui va créer un canal et appele l'application n utilisant**cmd.exe \/c** \(ou **command.exe \/c**\).  
  
## Exemple  
  
```  
// crt_spawn.c  
// This program accepts a number in the range  
// 1-8 from the command line. Based on the number it receives,  
// it executes one of the eight different procedures that  
// spawn the process named child. For some of these procedures,  
// the CHILD.EXE file must be in the same directory; for  
// others, it only has to be in the same path.  
//  
  
#include <stdio.h>  
#include <process.h>  
  
char *my_env[] =  
{  
   "THIS=environment will be",  
   "PASSED=to child.exe by the",  
   "_SPAWNLE=and",  
   "_SPAWNLPE=and",  
   "_SPAWNVE=and",  
   "_SPAWNVPE=functions",  
   NULL  
};  
  
int main( int argc, char *argv[] )  
{  
   char *args[4];  
  
   // Set up parameters to be sent:   
   args[0] = "child";  
   args[1] = "spawn??";  
   args[2] = "two";  
   args[3] = NULL;  
  
   if (argc <= 2)  
   {  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
  
   switch (argv[1][0])   // Based on first letter of argument   
   {  
   case '1':  
      _spawnl( _P_WAIT, argv[2], argv[2], "_spawnl", "two", NULL );  
      break;  
   case '2':  
      _spawnle( _P_WAIT, argv[2], argv[2], "_spawnle", "two",   
               NULL, my_env );  
      break;  
   case '3':  
      _spawnlp( _P_WAIT, argv[2], argv[2], "_spawnlp", "two", NULL );  
      break;  
   case '4':  
      _spawnlpe( _P_WAIT, argv[2], argv[2], "_spawnlpe", "two",   
                NULL, my_env );  
      break;  
   case '5':  
      _spawnv( _P_OVERLAY, argv[2], args );  
      break;  
   case '6':  
      _spawnve( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   case '7':  
      _spawnvp( _P_OVERLAY, argv[2], args );  
      break;  
   case '8':  
      _spawnvpe( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   default:  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
   printf( "from SPAWN!\n" );  
}  
```  
  
  **sortie du processus enfant**  
**Du SPAWN \!**   
## Voir aussi  
 [Contrôle de processus et d'environnement](../c-runtime-library/process-and-environment-control.md)   
 [abort](../c-runtime-library/reference/abort.md)   
 [atexit](../c-runtime-library/reference/atexit.md)   
 [\_exec, \_wexec, fonctions](../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../c-runtime-library/reference/system-wsystem.md)