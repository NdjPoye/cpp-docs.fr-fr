---
title: "Fonctions JScript des Assistants C++ | Microsoft Docs"
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
  - "méthodes JScript de l'Assistant"
  - "méthodes JScript de l'Assistant, créer des Assistants C++"
ms.assetid: f3046c56-cf67-4aaa-919e-8c066bfb6760
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions JScript des Assistants C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[AddATLSupportToProject](../ide/addatlsupporttoproject.md)|Ajoute la prise en charge ATL à un projet MFC.|  
|[AddCoclassFromFile](../ide/addcoclassfromfile.md)|Affiche et insère dans le fichier .idl du projet un fichier modèle qui contient une coclasse.|  
|[AddCommonConfig](../ide/addcommonconfig.md)|Ajoute les configurations par défaut au projet.|  
|[AddFilesToProject](../ide/addfilestoproject.md)|Ajoute au projet tous les fichiers fondés sur la liste du fichier Templates.inf.|  
|[AddInterfaceFromFile](../ide/addinterfacefromfile.md)|Affiche et insère dans le fichier IDL du projet un fichier modèle qui contient une interface.|  
|[CanAddATLClass](../ide/canaddatlclass.md)|L'Assistant appelle cette fonction pour vérifier si le projet est compatible avec l'Assistant code sur le point d'être exécuté \(en d'autres termes, une classe ATL est acceptée\).<br /><br /> L'Assistant appelle cette fonction lorsque le paramètre PREPROCESS\_FUNCTION figure dans le [fichier .vsz du contrôle du projet](../ide/dot-vsz-file-project-control.md) et vérifie si le [Visual C\+\+ Code Model](http://msdn.microsoft.com/fr-fr/dd6452c2-1054-44a1-b0eb-639a94a1216b) est disponible.  Si ce n'est pas le cas, la fonction signale une erreur et retourne **false**.|  
|[CanAddClass](../ide/canaddclass.md)|L'Assistant appelle cette fonction lorsqu'il trouve le paramètre PREPROCESS\_FUNCTION dans le fichier .vsz du contrôle du projet.<br /><br /> La fonction vérifie si l'objet de modèle de code Visual C\+\+ est disponible.  Si ce n'est pas le cas, la fonction signale une erreur et retourne **false**.|  
|[CanAddMFCClass](../ide/canaddmfcclass.md)|L'Assistant appelle cette fonction pour vérifier si le projet est compatible avec l'Assistant Code sur le point d'être exécuté \(en d'autres termes, s'il peut accepter une classe MFC\).<br /><br /> L'Assistant appelle cette fonction lorsqu'il trouve le paramètre PREPROCESS\_FUNCTION dans le fichier .vsz du contrôle du projet et vérifie si l'objet de modèle de code Visual C\+\+ est disponible.  Si ce n'est pas le cas, la fonction signale une erreur et retourne **false**.|  
|[CanAddNonAttributed](../ide/canaddnonattributed.md)|Indique si le projet prend en charge les objets ATL avec et sans attributs.|  
|[CanUseFileName](../ide/canusefilename.md)|Vérifie si un fichier existe.  Dans ce cas, l'Assistant demande à l'utilisateur à fusionner le code qui doit être ajouté au fichier existant.|  
|[ConvertProjectToAttributed](../ide/convertprojecttoattributed.md)|Convertit un projet ATL en projet avec attributs.|  
|[CreateInfFile](../ide/createinffile.md)|Crée le fichier Templates.inf.|  
|[CreateProject](../ide/createproject.md)|Crée un projet C\+\+.|  
|[CreateSafeName](../ide/createsafename.md)|Génère un nom convivial C\+\+.|  
|[DeleteFile](../ide/deletefile.md)|Supprime le fichier spécifié.|  
|[DoesIncludeExist](../ide/doesincludeexist.md)|Indique si une instruction `#include` existe dans un fichier.|  
|[GetCodeForDllCanUnloadNow](../ide/getcodefordllcanunloadnow.md)|Récupère le code nécessaire au déchargement de la DLL.|  
|[GetCodeForDllGetClassObject](../ide/getcodefordllgetclassobject.md)|Récupère le code de l'objet de classe de la DLL.|  
|[GetCodeForDllRegisterServer](../ide/getcodefordllregisterserver.md)|Récupère le code nécessaire à l'inscription d'un serveur.|  
|[GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)|Récupère le code nécessaire à l'annulation de l'inscription d'un serveur.|  
|[GetCodeForExitInstance](../ide/getcodeforexitinstance.md)|Fonction d'assistance permettant d'obtenir le texte de `ExitInstance`.|  
|[GetCodeForInitInstance](../ide/getcodeforinitinstance.md)|Fonction d'assistance permettant d'obtenir le texte de [InitInstance](../Topic/CWinApp::InitInstance.md).|  
|[GetExportPragmas](../ide/getexportpragmas.md)|Récupère les pragmas nécessaires à l'exportation des fonctions.|  
|[GetInterfaceClasses](../ide/getinterfaceclasses.md)|Retourne l'objet `VCCodeClass` associé à une interface.|  
|[GetInterfaceType](../ide/getinterfacetype.md)|Retourne le type d'interface \(par exemple, personnalisée, double, dispinterface, oleautomation\).|  
|[GetMaxID](../ide/getmaxid.md)|Retourne le `dispid` le plus élevé à partir des membres de cette interface et de toutes ses bases.|  
|[GetMemberfunction](../ide/getmemberfunction.md)|Retourne un objet de fonction fondé sur le nom donné.|  
|[GetProjectFile](../ide/getprojectfile.md)|Retourne le nom de fichier du type des fichiers par projet \(.rc, .idl, par exemple\).|  
|[GetProjectPath](../ide/getprojectpath.md)|Retourne le chemin d'accès du répertoire du projet.|  
|[GetRuntimeErrorDesc](../ide/getruntimeerrordesc.md)|Retourne une description du type d'exception.|  
|[GetUniqueFileName](../ide/getuniquefilename.md)|Retourne un nom de fichier unique.|  
|[IncludeCodeElementDeclaration](../ide/includecodeelementdeclaration.md)|Ajoute l'instruction d'inclusion au paramètre `strInFile`, notamment l'en\-tête dans lequel `strCodeElemName` est implémenté, si un en\-tête de ce type existe dans le projet.|  
|[InsertIntoFunction](../ide/insertintofunction.md)|Fonction d'assistance appelée dans `AddATLSupportToProject` pour insérer le code dans `InitInstance`.|  
|[IsATLProject](../ide/isatlproject.md)|Indique si le projet est fondé sur ATL.|  
|[IsAttributedProject](../ide/isattributedproject.md)|Indique si un projet comporte des attributs.|  
|[IsMFCProject](../ide/ismfcproject.md)|Vérifie si un projet est fondé sur MFC.|  
|[LineBeginsWith](../ide/linebeginswith.md)|Fonction d'assistance appelée dans `InsertIntoFunction` pour déterminer si une ligne commence par une chaîne spécifique.|  
|[OffsetToLineNumber](../ide/offsettolinenumber.md)|Recherche le numéro de ligne pour une position donnée dans le corps d'une fonction.|  
|[OnWizFinish](../ide/onwizfinish.md)|Appelée à partir du script HTML de l'Assistant lorsque l'utilisateur clique sur **Terminer**.  Appelle la méthode **Finish** du contrôle de l'Assistant.|  
|[RenderAddTemplate](../ide/renderaddtemplate.md)|Affiche un fichier modèle et l'ajoute en option au projet.|  
|[SetCommonPchSettings](../ide/setcommonpchsettings.md)|Définit l'en\-tête précompilé du projet.|  
|[SetErrorInfo](../ide/seterrorinfo.md)|Fournit des informations sur les erreurs.|  
|[SetFilters](../ide/setfilters.md)|Ajoute des filtres source, d'inclusion et de ressources pour les dossiers projet.|  
|[SetMergeProxySymbol](../ide/setmergeproxysymbol.md)|Fonction appelée par l'Assistant pour ajouter le symbole \_MERGE\_PROXYSTUB, si nécessaire.|  
|[SetNoPchSettings](../ide/setnopchsettings.md)|Définit les propriétés de configuration du projet lorsque aucun en\-tête précompilé n'est utilisé.|  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)