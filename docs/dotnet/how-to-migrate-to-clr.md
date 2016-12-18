---
title: "Comment&#160;: effectuer une migration vers /clr | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr (option du compilateur C++), porter vers"
  - "compiler du code natif (C++)"
  - "Interop (C++), /clr (option du compilateur)"
  - "interopérabilité (C++), /clr (option du compilateur)"
  - "migration (C++), /clr (option du compilateur)"
  - "mettre à niveau les applications Visual C++, /clr (option du compilateur)"
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
caps.latest.revision: 37
caps.handback.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: effectuer une migration vers /clr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique traite des problèmes qui surviennent lors de la compilation du code natif avec **\/clr** \(consultez [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md) pour plus d'informations\).  **\/clr** permet aux modules Visual C\+\+ d'appeler et d'être appelés depuis les assemblys .NET tout en conservant la compatibilité avec les modules non managés.  Voir [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md) et [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md) pour plus d'informations sur les avantages de la compilation avec **\/clr**.  
  
## Problèmes connus s'agissant de compilation de projets de bibliothèques avec \/clr  
 Visual Studio contient des problèmes connus lors de la compilation de projets de bibliothèque avec **\/clr** :  
  
-   Votre code peut interroger des types pendant l'exécution avec [CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md).  Toutefois, si un type est contenu dans un .dll MSIL \(compilé avec **\/clr**\), l'appel à [CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md) peut échouer s'il se produit avant l'exécution des constructeurs statiques dans le .dll managé \(ce problème ne se produit pas si l'appel FromName est effectué après l'exécution du code dans le .dll managé\).  Pour contourner ce problème, vous pouvez forcer la construction du constructeur statique managé en définissant une fonction dans le .dll managé, en l'exportant, puis en l'appelant à partir de l'application MFC native.  Par exemple :  
  
    ```  
    // Extension DLL Header file:  
    __declspec( dllexport ) void EnsureManagedInitialization () {  
       // managed code that won't be optimized away  
       System::GC::KeepAlive(System::Int32::MaxValue);  
    }  
    ```  
  
## Compilation avec Visual C\+\+  
 Avant toute utilisation de **\/clr** sur un module quelconque de votre projet, vous devez d'abord compiler et lier votre projet natif avec Visual Studio 2010.  
  
 Les étapes indiquées ci\-dessous, à suivre dans l'ordre, montrent le moyen le plus simple d'effectuer une compilation **\/clr**.  Il est important de compiler et d'exécuter votre projet après chacune de ces étapes.  
  
### Versions antérieures à Visual C\+\+ 2003  
 Si vous effectuez une mise à niveau vers Visual Studio 2010 à partir d'une version antérieure à Visual C\+\+ 2003, des erreurs de compilation liées à une meilleure conformité de Visual C\+\+ 2003 à la norme C\+\+ risquent d'apparaître  
  
### Mise à niveau à partir de Visual C\+\+ 2003  
 Les projets antérieurs générés avec Visual C\+\+ 2003 doivent également être compilés d'abord sans **\/clr**, étant donné que Visual Studio bénéficie d'une meilleure conformité aux normes ANSI\/ISO, et en raison de plusieurs nouveautés.  La modification sans doute la plus digne d'attention est [Fonctionnalités de sécurité dans le CRT](../c-runtime-library/security-features-in-the-crt.md).  Il est très probable que du code utilisant le CRT produise des avertissements de désapprobation.  Ces avertissements peuvent être supprimés, mais il est préférable d'effectuer une migration vers les nouvelles [Versions à la sécurité améliorée des fonctions CRT](../c-runtime-library/security-enhanced-versions-of-crt-functions.md), celles\-ci apportant des améliorations en termes de sécurité et pouvant éventuellement révéler des problèmes de sécurité dans votre code.  
  
### Mise à niveau à partir d'Extensions managées pour C\+\+  
 Pour les projets générés avec Visual C\+\+ .NET ou Visual C\+\+ 2003 qui utilisaient les Extensions managées pour C\+\+, il sera nécessaire d'apporter au moins une modification aux paramètres du projet, puisque ces extensions sont maintenant déconseillées.  En conséquence, le code écrit avec les extensions managées pour C\+\+ ne seront pas compilées sous **\/clr**.  Utilisez plutôt **\/clr:oldSyntax**.  
  
## Conversion du code C en C\+\+  
 Bien que Visual Studio puisse compiler des fichiers C, il est nécessaire de les convertir en C\+\+ pour une compilation **\/clr**.  Le nom de fichier actuel n'a pas à être modifié, vous pouvez utiliser **\/Tp** \(consultez [\/Tc, \/Tp, \/TC, \/TP \(Spécifier le type de fichier source\)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md)\). Notez que, bien que **\/clr** requiert des fichiers de code source C\+\+, il n'est pas nécessaire de refactoriser votre code pour utiliser des paradigmes orientés objet.  
  
 Il est très probable que le code C nécessitera des modifications une fois compilé sous la forme d'un fichier C\+\+.  Les règles de sécurité de type C\+\+ sont strictes, il faut donc que les conversions de types soient effectuées de façon explicite à l'aide de casts.  Par exemple, malloc retourne un pointeur void, mais peut être assigné à un pointeur vers n'importe quel type en C avec un cast :  
  
```  
int* a = malloc(sizeof(int));   // C code  
int* b = (int*)malloc(sizeof(int));   // C++ equivalent  
```  
  
 Les pointeurs fonction sont aussi strictement de type sécurisé en C\+\+, si bien qu'il faut modifier le code C suivant.  En C\+\+, le mieux est de créer un `typedef` qui définit le type du pointeur fonction, puis d'utiliser ce type pour effectuer un cast des pointeurs fonction :  
  
```  
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code  
typedef int(*MYPROC)(int);   // C++ equivalent  
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );  
```  
  
 En C\+\+, une fonction doit être soit prototypée soit complètement définie pour pouvoir être référencée ou appelée.  
  
 Les identificateurs utilisés en code C qui se trouvent être des mots clés en C\+\+ \(tels que `virtual`, `new`, `delete`, `bool`, `true`, `false`, etc.\) doivent être renommés.  Pour ce faire, on peut en général utiliser des opérations simples de recherche\/remplacement.  
  
 Enfin, les appels COM de style C requièrent l'utilisation explicite de la v\-table et du pointeur `this`, ce qui n'est pas le cas en C\+\+ :  
  
```  
COMObj1->lpVtbl->Method(COMObj, args);  // C code  
COMObj2->Method(args);  // C++ equivalent  
```  
  
## Reconfiguration des paramètres du projet  
 Après la compilation et l'exécution du projet dans Visual Studio 2010, vous devez créer des configurations de projet pour **\/clr** plutôt que modifier les configurations par défaut.  **\/clr** est incompatible avec certaines options du compilateur et la création de configurations séparées vous permet de générer votre projet comme natif ou managé.  Lorsque **\/clr** est sélectionné dans la boîte de dialogue Pages de propriétés, les paramètres du projet non compatibles avec **\/clr** sont désactivés \(et les options désactivées ne sont pas restaurées automatiquement si **\/clr** est désélectionné par la suite\).  
  
### Création des configurations d'un nouveau projet  
 Vous pouvez utiliser l'option **Copier les paramètres à partir de** dans la [New Project Configuration Dialog Box](http://msdn.microsoft.com/fr-fr/cca616dc-05a6-4fe3-bdc1-40c72a66f2be) pour créer une configuration de projet basée sur vos paramètres de projet existants.  Faites\-le une fois pour la configuration Debug et une fois également pour la configuration Release.  Les modifications suivantes peuvent alors être appliquées aux configurations spécifiques à **\/clr** uniquement, ce qui laisse intactes les configurations de projet d'origine.  
  
 Les projets qui utilisent des règles de génération personnalisées doivent faire l'objet d'une plus grande attention.  
  
 Cette étape a diverses conséquences sur les projets qui utilisent des makefiles.  Dans ce cas, une cible de génération distincte peut être configurée, ou une version spécifique destinée à la compilation sous **\/clr** peut être créée à partir d'une copie de l'original.  
  
### Modification des paramètres du projet  
 On peut sélectionner **\/clr** dans l'environnement de développement en suivant les instructions de [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  Comme mentionné précédemment, cette étape désactivera automatiquement les paramètres du projet incompatibles.  
  
> [!NOTE]
>  Lors de la mise à niveau d'une bibliothèque managée ou d'un projet de service Web à partir de Visual C\+\+ 2003, l'option du compilateur **\/Zl** est ajoutée dans la page de propriétés **Ligne de commande**.  Cela provoquera une erreur LNK2001.  La solution est de supprimer **\/Zl** de la page de propriétés **Ligne de commande**.  Pour plus d'informations, consultez [\/Zl \(Omettre le nom de la bibliothèque par défaut\)](../build/reference/zl-omit-default-library-name.md) et [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md).  Ou ajoutez msvcrt.lib et msvcmrt.lib à la propriété **Dépendances supplémentaires** de l'éditeur de liens.  
  
 Pour les projets générés avec des makefiles, les options du compilateur incompatibles doivent être manuellement désactivées une fois **\/clr** ajouté.  Consultez \/[Restrictions de \/clr](../build/reference/clr-restrictions.md) pour plus d'informations sur les options du compilateur incompatibles avec **\/clr**.  
  
### En\-têtes précompilés  
 Les en\-têtes précompilés sont pris en charge sous **\/clr**.  Toutefois, si vous ne compilez que quelques\-uns de vos fichiers CPP avec **\/clr** \(en compilant le reste en natif\), il faudra procéder à certaines modifications car les en\-têtes précompilés générés avec **\/clr** ne sont pas compatibles avec ceux qui sont générés sans **\/clr**.  Cette incompatibilité est due au fait que **\/clr** génère et requiert des métadonnées.  Les modules compilés avec **\/clr** ne peuvent donc pas utiliser d'en\-têtes précompilés qui n'incluent pas de métadonnées, et inversement les modules non **\/clr** ne peuvent pas utiliser de fichiers d'en\-tête précompilés qui contiennent des métadonnées.  
  
 La façon la plus simple de compiler un projet dont certains modules sont compilés avec **\/clr** est de désactiver complètement les en\-têtes précompilés. \(Dans la boîte de dialogue Pages de Propriétés du projet, ouvrez le nœud C\/C\+\+ et sélectionnez « En\-têtes précompilés ».  Puis modifiez la propriété Création\/utilisation d'un en\-tête précompilé en « Sans utiliser les en\-têtes précompilés »\).  
  
 Cependant, les en\-têtes précompilés offrant, en particulier pour les grands projets, une bien meilleure vitesse de compilation, la désactivation de cette fonctionnalité n'est pas souhaitable.  Dans ce cas, le mieux est de configurer les fichiers **\/clr** et non **\/clr** de façon à utiliser séparément les en\-têtes précompilés.  Cela peut être fait en une étape : effectuez une sélection multiple des modules à compiler avec **\/clr** à l'aide de l'Explorateur de solutions, cliquez avec le bouton droit sur le groupe et sélectionnez Propriétés.  Puis modifiez à la fois la propriété Création\/utilisation d'un en\-tête précompilé en spécifiant un nom de fichier et la propriété Création\/utilisation d'un en\-tête précompilé pour utiliser respectivement un nom de fichier d'en\-tête et un fichier PCH différents.  
  
## Résolution d'Erreurs  
 La compilation avec **\/clr** peut provoquer des erreurs de compilateur, d'éditeur de liens ou d'exécution.  Cette section expose les problèmes les plus courants.  
  
### Fusion des métadonnées  
 Utiliser des versions différentes de types de données peut provoquer une erreur de l'éditeur de liens si les métadonnées générées pour les deux types ne correspondent pas. \(Cela arrive généralement lorsque les membres d'un type sont définis de façon conditionnelle et que les conditions ne sont pas les mêmes pour tous les fichiers CPP qui utilisent le type\). Dans ce cas, l'éditeur de liens échoue, en ne rapportant que le nom de symbole et le nom du deuxième fichier OBJ dans lequel le type a été défini.  Il est souvent utile d'inverser l'ordre dans lequel les fichiers OBJ sont envoyés à l'éditeur de liens pour découvrir l'emplacement de l'autre version du type de données.  
  
### Interblocage du verrouillage du chargeur  
 Dans Visual C\+\+ .NET et Visual C\+\+ 2003, l'initialisation sous **\/clr** était susceptible de produire un interblocage non déterministe.  Ce problème est connu sous le nom d'« interblocage du verrouillage du chargeur ».  Dans Visual Studio 2010, cet interblocage est plus facile à éviter, il est détecté et rapporté au moment de l'exécution et n'est plus non déterministe.  Ce problème de verrouillage du chargeur peut encore se rencontrer, mais il est désormais beaucoup plus facile à éviter et à résoudre.  Consultez [Initialisation d'assemblys mixtes](../dotnet/initialization-of-mixed-assemblies.md) pour des informations détaillées, une aide et des solutions.  
  
### Export de données  
 Exporter des données DLL est source d'erreurs et n'est pas recommandé.  En effet, il n'est pas certain que la section Données d'une DLL puisse être initialisée avant qu'une certaine partie managée de la DLL ait été exécutée.  Référencez les métadonnées avec [\#using, directive](../preprocessor/hash-using-directive-cpp.md).  
  
### Visibilité du type  
 Les types natifs sont désormais privés par défaut.  Dans Visual C\+\+ .NET 2002 et Visual C\+\+ 2003, les types natifs étaient publics par défaut.  Un type natif peut donc se retrouver invisible en dehors de la DLL.  Vous pouvez résoudre cette erreur en ajoutant `public` à ces types.  Pour plus d'informations, consultez [Visibilité de type et de membre](../misc/type-and-member-visibility.md).  
  
### Virgule flottante et problèmes d'alignement  
 `__controlfp` n'est pas pris en charge par le Common Language Runtime \(consultez [\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md) pour plus d'informations\).  Le CLR ne respectera pas non plus [align](../cpp/align-cpp.md).  
  
### Initialisation de COM  
 Le Common Language Runtime initialise automatiquement COM lorsqu'un module est initialisé \(lorsque COM est initialisé automatiquement, il est exécuté en tant que MTA\).  En conséquence, initialiser COM explicitement génère des codes de retour qui indiquent que COM est déjà initialisé.  Toute tentative d'initialisation explicite de COM sur un modèle de thread alors que le CLR a déjà initialisé COM sur un autre modèle de thread peut provoquer le blocage de votre application.  
  
 Le Common Language Runtime démarre par défaut COM en tant que MTA ; utilisez [\/CLRTHREADATTRIBUTE \(Définir l'attribut de thread CLR\)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md) pour modifier cela.  
  
### Problèmes de performances  
 Il est possible de constater une diminution des performances lorsque les méthodes C\+\+ natives générées en MSIL sont appelées indirectement \(par appels de fonction virtuelle ou à l'aide de pointeurs fonction\).  Pour en savoir plus à ce sujet, consultez [Double conversion de code \(thunking\)](../dotnet/double-thunking-cpp.md).  
  
 En passant de natif à MSIL, vous remarquerez une augmentation de la taille de votre jeu de travail.  C'est parce que le Common Language Runtime fournit de nombreuses fonctionnalités visant à garantir le bon fonctionnement des programmes.  Si votre application **\/clr** ne s'exécute pas correctement, vous pouvez activer C4793 \(désactivé par défaut\) ; voir [Avertissement du compilateur \(niveaux 1 et 3\) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md) pour plus d'informations.  
  
### Pannes lors de la fermeture du programme  
 Dans certains cas, le CLR peut quitter avant la fin de l'exécution de votre code managé.  L'utilisation de `std::set_terminate` et `SIGTERM` peut en être la cause.  Pour plus d'informations, consultez [signal, constantes](../c-runtime-library/signal-constants.md) et [set\_terminate](../Topic/set_terminate%20\(%3Cexception%3E\).md).  
  
## Utilisation des nouvelles fonctionnalités Visual C\+\+  
 Une fois votre application compilée, liée et exécutée, vous pouvez commencer à utiliser des fonctionnalités .NET dans n'importe quel module compilé avec **\/clr**.  Pour plus d'informations, consultez [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).  
  
 Si vous avez utilisé Extensions managées pour C\+\+, vous pouvez convertir votre code afin d'utiliser la nouvelle syntaxe.  Pour un résumé des différences syntaxiques, consultez [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/fr-fr/edbded88-7ef3-4757-bd9d-b8f48ac2aada).  Pour plus d'informations sur la conversion d'Extensions managées pour C\+\+, consultez [Initiation à la migration de C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md).  
  
 Pour plus d'informations sur la programmation .NET en Visual C\+\+, consultez :  
  
-   [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
  
-   [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)  
  
-   [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)