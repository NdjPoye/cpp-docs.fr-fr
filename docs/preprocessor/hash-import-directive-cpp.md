---
title: "#import, directive (C++) | Microsoft Docs"
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
  - "#import"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#import (directive)"
  - ".tlh (fichiers)"
  - "COM, fichier d'en-tête de bibliothèque de types"
  - "directive import (#import)"
  - "préprocesseur, directives"
  - "tlbid (commutateur)"
  - "tlh (fichiers)"
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #import, directive (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Utilisé pour incorporer les informations d'une bibliothèque de types.  Le contenu de la bibliothèque de types est converti en classes C\+\+, qui décrivent principalement les interfaces COM.  
  
## Syntaxe  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
#### Paramètres  
 *filename*  
 Spécifie la bibliothèque de types à importer.  `filename` peut avoir l'une des valeurs suivantes :  
  
-   Nom d'un fichier qui contient une bibliothèque de types, par exemple un fichier .olb, .tlb ou .dll.  Le mot clé, **file:**, peut précéder chaque nom de fichier.  
  
-   Progid d'un contrôle dans la bibliothèque de types.  Le mot clé, **progid:**, peut précéder chaque progid.  Par exemple :  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     Pour plus d'informations sur les ProgID, consultez [Spécification de l'ID de localisation et du numéro de version](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).  
  
     Notez que lorsque vous compilez avec un compilateur croisé sur un système d'exploitation 64 bits, le compilateur ne peut lire que la ruche du Registre 32 bits.  Vous pouvez utiliser le compilateur 64 bits natif pour générer et inscrire une bibliothèque de types 64 bits.  
  
-   ID de bibliothèque de la bibliothèque de types.  Le mot clé, **libid:**, peut précéder chaque ID de bibliothèque.  Par exemple :  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     Si vous ne spécifiez pas la version ou le lcid, les [règles](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) qui sont appliquées à **progid:** sont également appliquées à **libid:**.  
  
-   Fichier exécutable \(.exe\).  
  
-   Fichier de bibliothèque \(.dll\) contenant une ressource de bibliothèque de types \(telle que .ocx\).  
  
-   Document composite contenant une bibliothèque de types.  
  
-   Tout autre format de fichier pouvant être compris par l'API **LoadTypeLib**.  
  
 `attributes`  
 Un ou plusieurs [attributs \#import](#_predir_the_23import_directive_import_attributes).  Sépare les attributs par un espace ou une virgule.  Par exemple :  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only  
```  
  
 ou  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only  
```  
  
## Notes  
  
##  <a name="_predir_the_23import_directive_searchorderforfilename"></a> Ordre de recherche du nom de fichier  
 *filename* est éventuellement précédé d'une spécification de répertoire.  Le nom de fichier doit désigner un fichier existant.  La différence entre les deux formes de syntaxe provient de l'ordre dans lequel le préprocesseur recherche les fichiers de bibliothèque de type lorsque le chemin d'accès est spécifié de manière incomplète.  
  
|Forme syntaxique|Action|  
|----------------------|------------|  
|Forme avec guillemets|Indique au préprocesseur de rechercher les fichiers bibliothèques de types dans le répertoire du fichier qui contient l'instruction `#import`, puis dans les répertoires des fichiers qui incluent \(`#include`\) ce fichier.  Le préprocesseur explore ensuite les chemins d'accès spécifiés ci\-dessous.|  
|Forme avec crochets pointus|Indique au préprocesseur de rechercher les fichiers bibliothèques de types en utilisant les chemins d'accès suivants :<br /><br /> 1.  Liste du chemin d'accès de la variable d'environnement **PATH**<br />2.  Liste du chemin d'accès de la variable d'environnement **LIB**<br />3.  Chemin d'accès spécifié par l'option du compilateur \/I \(répertoires Include supplémentaires\), sauf si le compilateur recherche une bibliothèque de types référencée à partir d'une autre bibliothèque de types avec l'attribut [no\_registry](../preprocessor/no-registry.md).|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> Spécification de l'ID de localisation et du numéro de version  
 Lorsque vous spécifiez un progid, vous pouvez également spécifier l'ID de localisation et le numéro de version du progid.  Par exemple :  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
 Si vous ne spécifiez pas d'ID de localisation, un progid est choisi selon les règles suivantes :  
  
-   S'il existe un seul ID de localisation, celui\-ci est utilisé.  
  
-   S'il existe plusieurs ID de localisation, le premier ayant le numéro de version 0, 9 ou 409 est utilisé.  
  
-   S'il existe plusieurs ID de localisation et qu'aucun d'entre eux n'est 0, 9 ou 409, le dernier est utilisé.  
  
-   Si vous ne spécifiez pas de numéro de version, la version la plus récente est utilisée.  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a> Fichiers d'en\-tête créés par l'importation  
 `#import` crée deux fichiers d'en\-tête qui reconstruisent le contenu de la bibliothèque de types dans le code source C\+\+.  Le fichier d'en\-tête principal est similaire à celui produit par le compilateur MIDL \(Microsoft Interface Definition Langage\), mais avec un code et des données supplémentaires générés par le compilateur.  Le [fichier d'en\-tête principal](#_predir_the_primary_type_library_header_file) possède le même nom de base que la bibliothèque de types, suivi d'une extension .TLH.  Le fichier d'en\-tête secondaire possède le même nom de base que la bibliothèque de types, avec une extension .TLI.  Il contient les implémentations des fonctions membres générées par le compilateur, et est inclus \(`#include`\) dans le fichier d'en\-tête principal.  
  
 Si vous importez une propriété dispinterface qui utilise des paramètres byref, \#import ne générera pas l'instruction \_\_declspec\([propriété](../cpp/property-cpp.md)\) pour la fonction.  
  
 Les deux fichiers d'en\-tête sont placés dans le répertoire de sortie spécifié par l'option \/Fo \(Nom du fichier objet\).  Ils sont ensuite lus et compilés par le compilateur comme si le fichier d'en\-tête principal était nommé par une directive `#include`.  
  
 Les optimisations de compilateur suivantes sont fournies avec la directive `#import` :  
  
-   Le fichier d'en\-tête, une fois créé, porte le même horodatage que la bibliothèque de types.  
  
-   Lorsque `#import` est traité, le compilateur contrôle d'abord si l'en\-tête existe et s'il est à jour.  Si oui, il est inutile de le recréer.  
  
 La directive `#import` participe également à une régénération minimale et peut être placée dans un fichier d'en\-tête précompilé.  Pour plus d'informations, consultez [Création de fichiers d'en\-tête précompilés](../build/reference/creating-precompiled-header-files.md).  
  
###  <a name="_predir_the_primary_type_library_header_file"></a> Fichier d'en\-tête principal de bibliothèque de types  
 Le fichier d'en\-tête principal de bibliothèque de types se compose de sept sections :  
  
-   Zones fixes de titre : se composent des commentaires, de l'instruction `#include` pour COMDEF.H \(qui définit des macros standard utilisées dans l'en\-tête\) et d'autres informations de configuration diverses.  
  
-   Références anticipées et typedefs : se composent de déclarations de structure comme `struct IMyInterface` et de définitions de types \(typedefs\).  
  
-   Déclarations de pointeur intelligent : la classe de modèle `_com_ptr_t` est une implémentation de pointeur intelligent qui encapsule des pointeurs d'interface et élimine la nécessité d'appeler les fonctions `AddRef`, **Release**, `QueryInterface`.  En outre, elle masque l'appel de `CoCreateInstance` en créant un nouvel objet COM.  Cette section utilise l'instruction macro **\_COM\_SMARTPTR\_TYPEDEF** pour établir les typedefs des interfaces COM comme spécialisations de modèle de la classe de modèles [\_com\_ptr\_t](../cpp/com-ptr-t-class.md).  Par exemple, pour l'interface **IMyInterface**, le fichier .TLH contiendra :  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     ce que le compilateur développe en :  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     Le type `IMyInterfacePtr` peut alors être utilisé à la place du pointeur d'interface brut `IMyInterface*`.  Par conséquent, il n'est pas nécessaire d'appeler les différentes fonctions membres **IUnknown**  
  
-   Déclarations de typeinfo : se composent essentiellement des définitions de classe et d'autres éléments exposant les différents éléments de typeinfo retournés par **ITypeLib:GetTypeInfo**.  Dans cette section, chaque typeinfo de la bibliothèque de types est répercuté dans l'en\-tête en fonction des informations de `TYPEKIND`.  
  
-   Ancienne définition de GUID facultative : contient les initialisations des constantes GUID nommées.  Les noms se présentent sous la forme **CLSID\_CoClass** et **IID\_Interface**, semblables à ceux générés par le compilateur MIDL.  
  
-   Instruction `#include` pour l'en\-tête de bibliothèque de types secondaires.  
  
-   Zones fixes de pied de page : incluent actuellement `#pragma pack(pop)`.  
  
 Toutes les sections, sauf la section de zones fixes de titre et de zones fixes de pied de page, sont placées dans un espace de noms portant le nom spécifié par l'instruction **library** dans le fichier IDL d'origine.  Vous pouvez utiliser les noms de l'en\-tête de la bibliothèque de types en spécifiant une qualification explicite avec le nom de l'espace de noms ou en incluant l'instruction suivante :  
  
```  
using namespace MyLib;  
```  
  
 immédiatement après l'instruction `#import` dans le code source.  
  
 L'espace de noms peut être supprimé en utilisant l'attribut [no\_namespace](#_predir_no_namespace) de la directive `#import`.  Toutefois, la suppression de l'espace de noms peut entraîner des collisions de noms.  L'espace de noms peut également être renommé par l'attribut [rename\_namespace](#_predir_rename_namespace).  
  
 Le compilateur fournit le chemin d'accès complet aux dépendances de bibliothèque de types requises par la bibliothèque de types qu'il traite actuellement.  Le chemin d'accès est écrit, sous forme de commentaires, dans l'en\-tête de bibliothèque de types \(.TLH\) que le compilateur génère pour chaque bibliothèque de types traitée.  
  
 Si une bibliothèque de types inclut des références aux types définis dans d'autres bibliothèques de types, le fichier .TLH inclura des commentaires du type suivant :  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
 Le nom de fichier réel dans le commentaire `#import` est le chemin d'accès complet de la bibliothèque de types à références croisées, tel qu'il est stocké dans le registre.  Si vous rencontrez des erreurs dues à des définitions de type manquantes, vérifiez les commentaires au début du .TLH pour voir quelles bibliothèques de types dépendants doivent être importées en premier.  Les erreurs possibles sont des erreurs de syntaxe, par exemple C2143, C2146, C2321, C2501 \(decl\-specifiers absents\) ou C2433 \(« inline » non autorisé dans la déclaration de données\) lors de la compilation du fichier .TLI.  
  
 Vous devez déterminer les commentaires de dépendance qui ne sont pas fournis par les en\-têtes systèmes, puis fournir une directive `#import` avant la directive `#import` de la bibliothèque de types dépendants pour résoudre les erreurs.  
  
 Pour plus d'informations, consultez l'article de la Base de connaissances « Les méthodes de Wrapper \#import peuvent provoquer une violation d'accès » \(n° 242527\) ou « Erreurs du compilateur lors de l'utilisation de \#import avec XML » \(n° 269194\).  Vous trouverez les articles de la Base de connaissances sur le média MSDN Library ou à l'adresse [http:\/\/support.microsoft.com\/support\/](http://support.microsoft.com/support/).  
  
##  <a name="_predir_the_23import_directive_import_attributes"></a> Attributs \#import  
 `#import` peut éventuellement inclure un ou plusieurs attributs.  Ces attributs demandent au compilateur de modifier le contenu des en\-têtes de bibliothèque de types.  Un symbole de barre oblique inverse \(**\\**\) peut être utilisé pour inclure des lignes supplémentaires dans une instruction `#import` unique.  Par exemple :  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
 Pour plus d'informations, consultez [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md).  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)   
 [Prise en charge COM du compilateur](../cpp/compiler-com-support.md)