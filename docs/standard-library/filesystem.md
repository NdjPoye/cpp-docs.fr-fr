---
title: "&lt;filesystem&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::directory_entry"
  - "filesystem/std::tr2::sys::recursive_directory_iterator"
  - "filesystem/std::tr2::sys::path"
  - "filesystem/std::tr2::sys::filesystem_error"
  - "filesystem/std::tr2::sys::directory_iterator"
  - "<filesystem>"
dev_langs: 
  - "C++"
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# &lt;filesystem&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez l’en\-tête \<filesystem\> pour accéder aux classes et aux fonctions qui manipulent et récupèrent des informations sur les chemins, les fichiers et les répertoires.  
  
## Syntaxe  
  
```cpp  
#include <filesystem>  
using namespace std::tr2::sys;  
```  
  
> [!IMPORTANT]
>  Dans C\+\+ 14, l’en\-tête \<filesystem\> n’est pas encore une norme C\+\+, même si sa normalisation est prévue dans sa forme plus ou moins actuelle d’ici C\+\+ 17.  
  
 Cet en\-tête prend en charge les systèmes de fichiers des deux grandes classes de systèmes d’exploitation : Microsoft Windows et Posix.  
  
 Bien que la plupart des fonctionnalités soit communes aux deux systèmes d’exploitation, ce document met l’accent sur les différences. Exemple :  
  
-   Windows prend en charge plusieurs noms de racines, par exemple c: ou \\\\nom\_réseau. Ainsi, un système de fichiers se compose d’une forêt d’arborescences, chacune ayant son propre répertoire racine, par exemple c:\\ ou \\\\nom\_réseau, et chacun ayant son propre répertoire actif, pour compléter un chemin relatif \(le contraire d’un chemin absolu\).  
  
-   Posix prend en charge une arborescence unique \(sans nom de la racine\), le répertoire racine unique \/ et un répertoire actif unique.  
  
 Une autre différence importante réside dans la représentation native des chemins :  
  
-   Windows utilise une séquence wchar\_t terminée par un caractère Null, encodée au format UTF\-16 \(un ou deux éléments pour chaque caractère\).  
  
-   Posix utilise une séquence char terminée par un caractère Null, encodée au format UTF\-8 \(un ou plusieurs éléments pour chaque caractère\).  
  
-   Un objet de classe path stocke le chemin au format natif. Toutefois, il prend en charge la conversion \(avec simplicité\) entre ce format stocké et plusieurs formats externes :  
  
    -   Séquence char terminée par un caractère Null, encodée au format préconisé par le système d’exploitation.  
  
    -   Séquence char terminée par un caractère Null, encodée au format UTF\-8.  
  
    -   Séquence wchar\_t terminée par un caractère Null, encodée au format préconisé par le système d’exploitation.  
  
    -   Séquence char16\_t terminée par un caractère Null, encodée au format UTF\-16.  
  
    -   Séquence char32\_t terminée par un caractère Null, encodée au format UTF\-32.  
  
 Selon les besoins, les conversions entre ces représentations passent par une ou plusieurs facettes codecvt. Si aucun objet de paramètres régionaux spécifique n’est désigné, ces facettes sont obtenues à partir des paramètres régionaux globaux.  
  
 Il existe une autre différence, la précision avec laquelle chaque système d’exploitation vous permet de spécifier les autorisations d’accès aux fichiers ou répertoires :  
  
1.  Windows enregistre si un fichier est accessible en lecture seule ou en écriture, un attribut qui n’a aucune signification pour les répertoires.  
  
2.  Posix enregistre si un fichier peut être lu, écrit ou exécuté \(analysé, s’il s’agit d’un répertoire\) par son propriétaire, par le groupe de son propriétaire ou par tout le monde. En outre, il enregistre quelques autorisations supplémentaires.  
  
 Pour les deux systèmes, la structure imposée au chemin après le nom de la racine est la même. Pour le chemin c:\/abc\/xyz\/def.ext :  
  
-   Le nom de la racine est c:.  
  
-   Le répertoire racine est \/.  
  
-   Le chemin racine est c: \/.  
  
-   Le chemin relatif est abc\/xyz\/def.ext.  
  
-   Le chemin parent est c:\/abc\/xyz.  
  
-   Le nom de fichier est def.ext.  
  
-   La racine est def.  
  
-   L’extension est .ext.  
  
 Il existe une petite différence au niveau du **séparateur par défaut** dans la séquence de répertoires d’un chemin. Les deux systèmes d’exploitation vous permettent d’écrire une barre oblique \/. Toutefois, dans certains contextes, Windows préfère une barre oblique inverse \\.  
  
 Enfin, il existe une fonctionnalité importante qui concerne les objets path. Vous pouvez les utiliser partout où un argument appelé « nom de fichier » est nécessaire au sein des classes définies dans l’en\-tête \<fstream\>.  
  
 Pour plus d’informations et d’exemples de code, consultez [Navigation dans le système de fichiers \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## Classes  
  
|Nom|Description|  
|---------|-----------------|  
|directory\_entry, classe|Décrit un objet retourné par un directory\_iterator ou un recursive\_directory\_iterator et qui contient des informations sur un|  
|directory\_iterator, classe|Décrit un itérateur d'entrée qui parcourt les noms de fichiers dans un répertoire de système de fichiers.|  
|filesystem\_error, classe|Classe de base pour les exceptions qui sont levées pour signaler un dépassement de capacité du système de bas niveau.|  
|path, classe|Définit une classe qui stocke un objet de type de modèle `String` qui peut être utilisé comme nom de fichier.|  
|recursive\_directory\_iterator, classe|Décrit un itérateur d'entrée qui parcourt les noms de fichiers dans un répertoire de système de fichiers. L'itérateur peut également descendre dans des sous\-répertoires.|  
|[file\_status, classe](../standard-library/file-status-class.md)|Encapsule un `file_type`.|  
  
## Structures  
  
|Nom|Description|  
|---------|-----------------|  
|[space\_info, structure](../standard-library/space-info-structure.md)|Contient des informations sur un volume.|  
  
## Fonctions  
 [\<filesystem\>, fonctions](../standard-library/filesystem-functions.md)  
  
## Opérateurs  
 [\<filesystem\>, opérateurs](../standard-library/filesystem-operators.md)  
  
## Énumérations  
  
|Nom|Description|  
|---------|-----------------|  
|[copy\_option, énumération](../Topic/copy_option%20Enumeration%20%3Cfilesystem%3E.md)|Énumération utilisée avec [copy\_file](http://msdn.microsoft.com/fr-fr/4af7a9b0-8861-45ed-b84e-0307f0669d60) et qui détermine le comportement si un fichier de destination existe déjà.|  
|[directory\_options, énumération](../Topic/directory_options%20Enumeration.md)|Énumération qui spécifie les options pour les itérateurs de répertoire.|  
|[file\_type, énumération](../Topic/file_type%20Enumeration.md)|Énumération pour les types de fichiers.|  
|[perms, énumération](../Topic/perms%20Enumeration.md)|Type de masque de bits utilisé pour transmettre les autorisations et les options des autorisations|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)