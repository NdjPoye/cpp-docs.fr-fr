---
title: "errno, constantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ENOEXEC"
  - "ENOMEM"
  - "E2BIG"
  - "STRUNCATE"
  - "ENOENT"
  - "EMFILE"
  - "EBADF"
  - "EDEADLOCK"
  - "EXDEV"
  - "EILSEQ"
  - "EINVAL"
  - "EDOM"
  - "EACCES"
  - "ERANGE"
  - "ENOSPC"
  - "EAGAIN"
  - "EEXIST"
  - "ECHILD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "E2BIG (constante)"
  - "EACCES (constante)"
  - "EAGAIN (constante)"
  - "EBADF (constante)"
  - "ECHILD (constante)"
  - "EDEADLOCK (constante)"
  - "EDOM (constante)"
  - "EEXIST (constante)"
  - "EILSEQ (constante)"
  - "EINVAL (constante)"
  - "EMFILE (constante)"
  - "ENOENT (constante)"
  - "ENOEXEC (constante)"
  - "ENOMEM (constante)"
  - "ENOSPC (constante)"
  - "ERANGE (constante)"
  - "errno (constantes)"
  - "EXDEV (constante)"
  - "STRUNCATE (constante)"
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# errno, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <errno.h>  
```  
  
## Notes  
 Les valeurs **errno** sont des constantes affectées à [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) en cas de différentes conditions d'erreur.  
  
 ERRNO.H contient les définitions des valeurs **errno**.  Toutefois, toutes les définitions données dans ERRNO.H sont utilisées dans les systèmes d'exploitation Windows 32 bits.  Certaines des valeurs de ERRNO.H sont présentes pour assurer la compatibilité avec la famille des systèmes d'exploitation UNIX.  
  
 Les valeurs **errno** dans un système d'exploitation Windows 32 bits sont un sous\-ensemble des valeurs pour **errno** dans les systèmes de XENIX.  Par conséquent, la valeur **errno** n'est pas nécessairement le même que le code d'erreur réel retourné par un appel système Windows.  Pour accéder à un code d'erreur du système d'exploitation réel, utilisez la variable [\_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), qui contient cette valeur.  
  
 Les valeurs suivantes de **errno** sont prises en charge :  
  
 **ECHILD**  
 Aucun processus générés.  
  
 **EAGAIN**  
 Plus processus.  Une tentative de création d'un nouveau processus a échoué parce qu'il n'y a plus de slots de processus, ou il n'y a pas assez de mémoire, ou le niveau d'imbrication maximal a été atteint.  
  
 **E2BIG**  
 La liste d'arguments est trop longue.  
  
 **EACCES**  
 autorisation refusée ;  Le paramètre d'autorisation du fichier n'autorise pas l'accès spécifié.  Cette erreur indique une tentative d'accès au fichier \(ou, dans certains cas, un répertoire\) d'une manière qui est incompatible avec les attributs de fichier.  
  
 Par exemple, cette erreur peut se produire en cas de tentative de lecture à partir d'un fichier qui n'est pas ouvert, d'ouverture d'un fichier en lecture seule pour l'écriture, ou d'ouverture un dossier au lieu d'un fichier.  Dans les versions 3,0 du système d'exploitation MS\-DOS et versions ultérieures, **EACCES** peut également indiquer un verrou ou une violation d'un partage.  
  
 Cette erreur peut également se produire lors d'une tentative pour renommer un fichier ou un répertoire ou pour supprimer un dossier existant.  
  
 **EBADF**  
 Nombre incorrect de fichiers.  Il existe deux raisons : 1\) Le descripteur de fichier spécifié n'est pas une valeur valide et ne fait pas référence à un fichier ouvert. 2\) Tentative d'écriture dans un fichier ou un périphérique ouvert pour l'accès en lecture seule.  
  
 **EDEADLOCK**  
 Le blocage de ressource se produirait.  L'argument pour une fonction mathématique n'est pas dans le champ de la fonction.  
  
 **EDOM**  
 Argument mathématique.  
  
 **EEXIST**  
 Les fichiers existent.  Tentative de création d'un fichier existant.  Par exemple, **\_O\_CREAT** et les indicateurs de **\_O\_EXCL** sont spécifiés dans un appel de **\_open**, mais le fichier nommé existe déjà.  
  
 **EILSEQ**  
 Séquence non conforme d'octets \(par exemple, dans une chaîne MBCS\).  
  
 **EINVAL**  
 Argument non valide.  Une valeur non valide a été spécifiée pour l'un des arguments de fonction.  Par exemple, la valeur fournie pour l'origine lors du positionnement d'un pointeur de fichier \(au moyen d'un appel à **fseek**\) est avant le début du fichier.  
  
 **EMFILE**  
 Trop de fichiers ouverts.  Plus aucun descripteurs de fichiers n'est disponible, et des fichiers ne peuvent être ouverts.  
  
 **ENOENT**  
 Aucun fichier ou répertoire de la sorte.  Le fichier ou le répertoire spécifié n'existe pas ou est introuvable.  Ce message peut apparaître lorsqu'un fichier spécifié n'existe pas ou un composant d'un chemin d'accès ne spécifie pas un répertoire existant.  
  
 **ENOEXEC**  
 Erreur de format d'exécution.  Tentative d'exécution d'un fichier qui n'est pas exécutable ou qui a un format de fichier exécutable invalide.  
  
 **ENOMEM**  
 Pas assez de mémoire.  Mémoire insuffisante disponible pour l'opérateur.  Par exemple, ce message peut apparaître en cas d'insuffisance de la mémoire disponible pour exécuter un sous\-processus, ou lorsque la demande d'allocation dans un appel de **\_getcwd** ne peut pas être satisfaite.  
  
 **ENOSPC**  
 Aucun espace autorisé sur le périphérique.  Plus aucun espace pour écriture n'est disponible sur l'unité \(par exemple, si le disque est plein\).  
  
 **ERANGE**  
 Résultat trop volumineux.  Un argument d'une fonction mathématique est trop grand, provoquant ainsi la perte partielle ou totale de crédibilité du résultat.  Cette erreur peut également se produire dans d'autres fonctions lorsqu'un argument est supérieur à celui attendu \(par exemple, lorsque l'argument *de mémoire tampon* à **\_getcwd** est plus longue que prévu\).  
  
 **EXDEV**  
 Lien sur un autre périphérique.  Une tentative de déplacement un fichier vers une unité différente \(à l'aide de la fonction **rename** \).  
  
 **STRUNCATE**  
 Une copie ou une concaténation de chaîne a provoqué une chaîne tronquée.  Consultez [\_TRUNCATE](../c-runtime-library/truncate.md).  
  
 Les valeurs suivantes sont prises en charge pour la compatibilité avec Posix.  Ce sont des valeurs requises sur les systèmes non POSIX.  
  
```  
#define E2BIG [argument list too long]  
#define EACCES [permission denied]  
#define EADDRINUSE [address in use]  
#define EADDRNOTAVAIL [address not available]  
#define EAFNOSUPPORT [address family not supported]  
#define EAGAIN [resource unavailable try again]  
#define EALREADY [connection already in progress]  
#define EBADF [bad file descriptor]  
#define EBADMSG [bad message]  
#define EBUSY [device or resource busy]  
#define ECANCELED [operation canceled]  
#define ECHILD [no child process]  
#define ECONNABORTED [connection aborted]  
#define ECONNREFUSED [connection refused]  
#define ECONNRESET [connection reset]  
#define EDEADLK [resource deadlock would occur]  
#define EDESTADDRREQ [destination address required]  
#define EDOM [argument out of domain]  
#define EEXIST [file exists]  
#define EFAULT [bad address]  
#define EFBIG [file too large]  
#define EHOSTUNREACH [host unreachable]  
#define EIDRM [identifier removed]  
#define EILSEQ [illegal byte sequence]  
#define EINPROGRESS [operation in progress]  
#define EINTR [interrupted]  
#define EINVAL [invalid argument]  
#define EIO [io error]  
#define EISCONN [already connected]  
#define EISDIR [is a directory]  
#define ELOOP [too many synbolic link levels]  
#define EMFILE [too many files open]  
#define EMLINK [too many links]  
#define EMSGSIZE [message size]  
#define ENAMETOOLONG [filename too long]  
#define ENETDOWN [network down]  
#define ENETRESET [network reset]  
#define ENETUNREACH [network unreachable]  
#define ENFILE [too many files open in system]  
#define ENOBUFS [no buffer space]  
#define ENODATA [no message available]  
#define ENODEV [no such device]  
#define ENOENT [no such file or directory]  
#define ENOEXEC [executable format error]  
#define ENOLCK [no lock available]  
#define ENOLINK [no link]  
#define ENOMEM [not enough memory]  
#define ENOMSG [no message]  
#define ENOPROTOOPT [no protocol option]  
#define ENOSPC [no space on device]  
#define ENOSR [no stream resources]  
#define ENOSTR [not a stream]  
#define ENOSYS [function not supported]  
#define ENOTCONN [not connected]  
#define ENOTDIR [not a directory]  
#define ENOTEMPTY [directory not empty]  
#define ENOTRECOVERABLE [state not recoverable]  
#define ENOTSOCK [not a socket]  
#define ENOTSUP [not supported]  
#define ENOTTY [inappropriate io control operation]  
#define ENXIO [no such device or address]  
#define EOPNOTSUPP [operation not supported]  
#define EOTHER [other]  
#define EOVERFLOW [value too large]  
#define EOWNERDEAD [owner dead]  
#define EPERM [operation not permitted]  
#define EPIPE [broken pipe]  
#define EPROTO [protocol error]  
#define EPROTONOSUPPORT [protocol not supported]  
#define EPROTOTYPE [wrong protocol type]  
#define ERANGE [result out of range]  
#define EROFS [read only file system]  
#define ESPIPE [invalid seek]  
#define ESRCH [no such process]  
#define ETIME [stream timeout]  
#define ETIMEDOUT [timed out]  
#define ETXTBSY [text file busy]  
#define EWOULDBLOCK [operation would block]  
#define EXDEV [cross device link]  
```  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)