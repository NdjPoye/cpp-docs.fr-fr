---
title: "Component Extensions for Runtime Platforms | Microsoft Docs"
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
  - "what's new [C++], keywords"
  - "what's new [C++], language features"
  - "Visual C++, keywords"
  - "keywords [C++]"
  - "Managed Extensions for C++, replacement syntax"
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
caps.latest.revision: 77
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 77
---
# Component Extensions for Runtime Platforms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ fournit des extensions de langage pour vous aider à programmer par rapport à des plateformes d'exécution.  À l'aide de [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]\), vous pouvez programmer des applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] et des composants qui se compilent en code natif.  Bien que vous puissiez créer des applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] par programmation directe par rapport aux interfaces COM [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], en utilisant [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], vous pouvez utiliser des constructeurs, des exceptions et d'autres langages de programmation C\+\+ modernes.  Pour activer la programmation en C\+\+ dans un environnement d'exécution managé sur la plateforme .NET, vous pouvez utiliser [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  
  
 **Deux runtimes, un ensemble d'extensions**  
  
 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] est un sous\-ensemble de [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  Pour les extensions communes à [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] et [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)], la sémantique dépend de votre choix de cibler le Common Language Runtime \(CLR\) ou [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Pour compiler votre application pour qu'elle s'exécute sur [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], spécifiez l'option de compilateur **\/ZW**.  Pour la compiler pour qu'elle s'exécute sur le CLR, spécifiez l'option de compilateur **\/clr**.  Ces commutateurs sont définis automatiquement quand vous utilisez Visual Studio pour créer un projet.  
  
 Pour plus d'informations sur la création d'applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] en C\+\+, consultez [Feuille de route pour les applications Windows Runtime en C\+\+](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx).  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] étend la norme ISO\/ANSI C\+\+. Sa définition entre dans la norme Ecma [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  Pour plus d'informations, consultez [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
## Mots clés de type de données  
 Les extensions de langage incluent des *mots clés d'agrégation*, à savoir des mots clés constitués de deux jetons séparés par un espace blanc.  Les jetons peuvent avoir une signification précise quand ils sont utilisés séparément et une autre signification quand ils sont utilisés ensemble.  Par exemple, le mot « ref » est un identificateur ordinaire et le mot « class » est un mot clé qui déclare une classe native.  Mais quand ces mots sont combinés pour former `ref class`, le mot clé d'agrégation obtenu permet de déclarer une entité connue en tant que *classe runtime*.  
  
 Les extensions incluent également des mots clés *contextuels*.  Un mot clé est considéré comme contextuel en fonction du type d'instruction qui le contient et de son positionnement dans cette instruction.  Par exemple, le jeton « property » peut être un identificateur ou il peut déclarer un type spécial de membre de classe publique.  
  
 Le tableau suivant répertorie les mots clés de l'extension du langage C\+\+.  
  
|Mot clé|Contextuel|Objectif|Référence|  
|-------------|----------------|--------------|---------------|  
|`ref class`<br /><br /> `ref struct`|Non|Déclare une classe.|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`value class`<br /><br /> `value struct`|Non|Déclare une classe de valeur.|[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)|  
|`interface class`<br /><br /> `interface struct`|Non|Déclare une interface.|[interface class](../windows/interface-class-cpp-component-extensions.md)|  
|`enum class`<br /><br /> `enum struct`|Non|Déclare une énumération.|[enum, classe](../windows/enum-class-cpp-component-extensions.md)|  
|`property`|Oui|Déclare une propriété.|[property](../windows/property-cpp-component-extensions.md)|  
|`delegate`|Oui|Déclare un délégué.|[délégué](../windows/delegate-cpp-component-extensions.md)|  
|`event`|Oui|Déclare un événement.|[event](../windows/event-cpp-component-extensions.md)|  
  
## Spécificateurs de substitution  
 Vous pouvez utiliser les mots clés suivants pour qualifier le comportement de substitution pour la dérivation.  Bien que le mot clé `new` ne soit pas une extension de C\+\+, il est répertorié ici car il peut être utilisé dans un autre contexte.  Certains spécificateurs sont également valides pour la programmation native.  Pour plus d'informations, consultez [Comment : déclarer des spécificateurs de substitution dans les compilations natives](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
|Mot clé|Contextuel|Objectif|Référence|  
|-------------|----------------|--------------|---------------|  
|`abstract`|Oui|Indique que les fonctions ou classes sont abstraites.|[abstract](../windows/abstract-cpp-component-extensions.md)|  
|`new`|Non|Indique qu'une fonction n'est pas une substitution d'une version de la classe de base.|[new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|  
|`override`|Oui|Indique qu'une méthode doit être une substitution d'une version de la classe de base.|[override](../windows/override-cpp-component-extensions.md)|  
|`sealed`|Oui|Empêche les classes d'être utilisées comme classes de base.|[sealed](../windows/sealed-cpp-component-extensions.md)|  
  
## Mots clés pour les génériques  
 Les mots clés suivants ont été ajoutés pour prendre en charge des types génériques.  Pour plus d'informations, consultez [Generics](../windows/generics-cpp-component-extensions.md).  
  
|Mot clé|Contextuel|Objectif|  
|-------------|----------------|--------------|  
|`generic`|Non|Déclare un type générique.|  
|`where`|Oui|Spécifie les contraintes appliquées à un paramètre de type générique.|  
  
## Mots clés divers  
 Les mots clés suivants ont été ajoutés aux extensions C\+\+.  
  
|Mot clé|Contextuel|Objectif|Référence|  
|-------------|----------------|--------------|---------------|  
|`finally`|Oui|Indique le comportement de gestion des exceptions par défaut.|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|  
|`for each, in`|Non|Énumère les éléments d'une collection.|[for each, in](../dotnet/for-each-in.md)|  
|`gcnew`|Non|Alloue des types sur le tas récupéré par le garbage collector.  À utiliser à la place de `new` et `delete`.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`ref new`|Oui|Alloue un type [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  À utiliser à la place de `new` et `delete`.|[ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|  
|`initonly`|Oui|Indique qu'un membre peut uniquement être initialisé lors de la déclaration ou dans un constructeur statique.|[initonly](../dotnet/initonly-cpp-cli.md)|  
|`literal`|Oui|Crée une variable littérale.|[literal](../windows/literal-cpp-component-extensions.md)|  
|`nullptr`|Non|Indique qu'un handle ou pointeur ne pointe pas vers un objet.|[nullptr](../windows/nullptr-cpp-component-extensions.md)|  
  
## Constructions de modèle  
 Les constructions de langage suivantes sont implémentées comme modèles, plutôt que comme mots clés.  Si vous spécifiez l'option de compilateur **\/ZW**, elles sont définies dans l'espace de noms `lang`.  Si vous spécifiez l'option de compilateur **\/clr**, elles sont définies dans l'espace de noms `cli`.  
  
|Mot clé|Objectif|Référence|  
|-------------|--------------|---------------|  
|`array`|Déclare un tableau.|[Arrays](../windows/arrays-cpp-component-extensions.md)|  
|`interior_ptr`|\(CLR uniquement\) Pointe vers des données dans un type de référence.|[interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)|  
|`pin_ptr`|\(CLR uniquement\) Pointe vers des types de référence CLR pour supprimer temporairement le système de garbage collection.|[pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)|  
|`safe_cast`|Détermine et exécute la méthode de casting optimale pour un type de runtime.|[safe\_cast](../windows/safe-cast-cpp-component-extensions.md)|  
|`typeid`|\(CLR uniquement\) Récupère un objet <xref:System.Type?displayProperty=fullName> qui décrit le type ou l'objet donné.|[typeid](../windows/typeid-cpp-component-extensions.md)|  
  
## Déclarateurs  
 Les déclarateurs de type suivants demandent au runtime de gérer automatiquement la durée de vie et la suppression des objets alloués.  
  
|Opérateur|Objectif|Référence|  
|---------------|--------------|---------------|  
|`^`|Déclare un handle à un objet ; autrement dit, un pointeur vers un objet [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ou CLR qui est automatiquement supprimé quand il n'est plus utilisable.|[Handle sur l'opérateur Object \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|  
|`%`|Déclare une référence de suivi ; autrement dit, une référence vers un objet [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ou CLR qui est automatiquement supprimé quand il n'est plus utilisable.|[Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md)|  
  
## Constructions supplémentaires et rubriques connexes  
 Cette section répertorie les constructions de programmation supplémentaires, ainsi que les rubriques qui se rapportent au CLR.  
  
|Rubrique|Description|  
|--------------|-----------------|  
|[\_\_identifier \(C\+\+\/CLI\)](../windows/identifier-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et CLR\) Permet d'utiliser des mots clés en tant qu'identificateurs.|  
|[Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|\([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et CLR\) Permet à une fonction de prendre un nombre variable d'arguments.|  
|[Équivalents .NET Framework des types natifs C\+\+](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|Répertorie les types CLR qui sont utilisés à la place des types intégraux C\+\+.|  
|Modificateur `__declspec` [appdomain](../cpp/appdomain.md)|Modificateur `__declspec` qui impose que des variables statiques et globales existent par appdomain.|  
|[C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)|Décrit comment les casts de style C sont interprétées.|  
|Convention d'appel [\_\_clrcall](../cpp/clrcall.md)|Indique la convention d'appel conforme au CLR.|  
|`__cplusplus_cli`|[Macros prédéfinies](../preprocessor/predefined-macros.md)|  
|[Custom Attributes](../windows/custom-attributes-cpp.md)|Décrit comment définir vos propres attributs CLR.|  
|[Exception Handling](../windows/exception-handling-cpp-component-extensions.md)|Fournit une vue d'ensemble de la gestion des exceptions.|  
|[Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)|Montre comment les fonctions membres peuvent substituer les membres arbitraires.|  
|[Assemblys friend \(C\+\+\)](../dotnet/friend-assemblies-cpp.md)|Explique comment un assembly client peut accéder à tous les types dans un composant d'assembly.|  
|[Boxing](../windows/boxing-cpp-component-extensions.md)|Montre les conditions dans lesquelles les types de valeur sont boxed.|  
|[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|Explique comment détecter les caractéristiques des types au moment de la compilation.|  
|Pragmas [managé, non managé](../preprocessor/managed-unmanaged.md)|Montre comment les fonctions managées et non managées peuvent coexister dans le même module.|  
|Modificateur `__declspec` [processus](../cpp/process.md)|Modificateur `__declspec` qui impose que des variables statiques et globales existent par process.|  
|[Réflexion](../dotnet/reflection-cpp-cli.md)|Montre la version CLR des informations de type au moment de l'exécution.|  
|[String](../windows/string-cpp-component-extensions.md)|Décrit la conversion du compilateur des littéraux de chaîne en <xref:System.String>.|  
|[Type Forwarding \(C\+\+\/CLI\)](../windows/type-forwarding-cpp-cli.md)|Permet le déplacement d'un type dans un assembly d'expédition vers un autre assembly afin que le code client n'ait pas besoin d'être recompilé.|  
|[User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md)|Montre les attributs définis par l'utilisateur.|  
|[\#using, directive](../preprocessor/hash-using-directive-cpp.md)|Importe des assemblys externes.|  
|[Documentation XML](../ide/xml-documentation-visual-cpp.md)|Explique la documentation du code XML à l'aide de [\/doc \(Traiter les commentaires de documentation\)](../build/reference/doc-process-documentation-comments-c-cpp.md).|  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)