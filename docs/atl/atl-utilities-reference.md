---
title: "R&#233;f&#233;rence des utilitaires ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# R&#233;f&#233;rence des utilitaires ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL fournit le code pour les chemins et manipulation des URL sous forme de [CPathT](../atl/reference/cpatht-class.md) et d' [Aller\-retour](../atl/reference/curl-class.md).  Un pool de threads, [CThreadPool](../atl/reference/cthreadpool-class.md), peut être utilisé dans vos applications.  Ce code se trouve dans atlpath.h et atlutil.h.  
  
### Classes  
  
|||  
|-|-|  
|[Classe de CPathT](../atl/reference/cpatht-class.md)|Cette classe représente un chemin d'accès.|  
|[Classe de CDebugReportHook](../atl/reference/cdebugreporthook-class.md)|Utilisez cette classe pour envoyer des rapports de débogage vers un canal nommé.|  
|[Classe de CNonStatelessWorker](../atl/reference/cnonstatelessworker-class.md)|Accepte les demandes d'un pool de threads et les transmet à un objet de travail créé et détruit à chaque requête.|  
|[Classe de CNoWorkerThread](../atl/reference/cnoworkerthread-class.md)|Utilisez cette classe comme argument pour le paramètre de modèle d' `MonitorClass` mette en cache des classes si vous souhaitez désactiver la maintenance dynamique de cache.|  
|[CThreadPool de classe](../atl/reference/cthreadpool-class.md)|Cette classe fournit un pool de threads de travail qui traitent une file d'attente des éléments de travail.|  
|[Classe de boucle](../atl/reference/curl-class.md)|Cette classe représente une URL.  Elle vous permet de manipuler chaque élément de l'URL indépendamment des autres si l'analyse une chaîne existante d'URL ou de la génération d'une chaîne à partir de zéro.|  
|[Classe de CWorkerThread](../atl/reference/cworkerthread-class.md)|Cette classe crée un thread de travail ou utilise existant, attend un ou plusieurs handles d'objet de noyau, puis exécute une fonction cliente spécifiée lorsque l'une des poignées est signalé.|  
  
### Typedef  
  
|||  
|-|-|  
|[CPath](../Topic/CPath.md)|Une spécialisation de [CPathT](../atl/reference/cpatht-class.md) à l'aide de `CString`.|  
|[CPathA](../Topic/CPathA.md)|Une spécialisation de [CPathT](../atl/reference/cpatht-class.md) à l'aide de `CStringA`.|  
|[CPathW](../Topic/CPathW.md)|Une spécialisation de [CPathT](../atl/reference/cpatht-class.md) à l'aide de `CStringW`.|  
|[ATL\_URL\_PORT](../Topic/ATL_URL_PORT.md)|Le type utilisé par [Aller\-retour](../atl/reference/curl-class.md) pour spécifier un numéro de port.|  
  
### Enums  
  
|||  
|-|-|  
|[ATL\_URL\_SCHEME](../Topic/ATL_URL_SCHEME.md)|Les membres de cette énumération fournissent des constantes pour les modèles inclus par [Aller\-retour](../atl/reference/curl-class.md).|  
  
### Fonctions  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../Topic/AtlCanonicalizeUrl.md)|Appelez cette fonction pour rendre canonique une URL, notamment convertir les caractères et espaces potentiellement dangereux dans des séquences d'échappement.|  
|[AtlCombineUrl](../Topic/AtlCombineUrl.md)|Appelez cette fonction pour associer une URL de base et une URL relative dans une URL unique et canonique.|  
|[AtlEscapeUrl](../Topic/AtlEscapeUrl.md)|Appelez cette fonction pour convertir tous les caractères potentiellement dangereux en séquences d'échappement.|  
|[AtlGetDefaultUrlPort](../Topic/AtlGetDefaultUrlPort.md)|Appelez cette fonction pour obtenir le numéro de port par défaut associé à un protocole Internet particulier ou pour intriguer.|  
|[AtlHexValue](../Topic/AtlHexValue.md)|Appelez cette fonction pour obtenir la valeur numérique d'un chiffre hexadécimal.|  
|[AtlIsUnsafeUrlChar](../Topic/AtlIsUnsafeUrlChar.md)|Appelez cette fonction pour déterminer si un caractère est sécurisé à utiliser dans une URL.|  
|[AtlUnescapeUrl](../Topic/AtlUnescapeUrl.md)|Appelez cette fonction pour convertir des caractères d'échappement à leurs valeurs d'origine.|  
|[SystemTimeToHttpDate](../Topic/SystemTimeToHttpDate.md)|Appelez cette fonction pour convertir une heure système en une chaîne au format approprié pour une utilisation dans les en\-têtes HTTP.|  
|[ATLPath::AddBackslash](../Topic/ATLPath::AddBackslash.md)|Cette fonction est un wrapper surchargé pour [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).|  
|[ATLPath::AddExtension](../Topic/ATLPath::AddExtension.md)|Cette fonction est un wrapper surchargé pour [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).|  
|[ATLPath::Append](../Topic/ATLPath::Append.md)|Cette fonction est un wrapper surchargé pour [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).|  
|[ATLPath::BuildRoot](../Topic/ATLPath::BuildRoot.md)|Cette fonction est un wrapper surchargé pour [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).|  
|[ATLPath::Canonicalize](../Topic/ATLPath::Canonicalize.md)|Cette fonction est un wrapper surchargé pour [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).|  
|[ATLPath::Combine](../Topic/ATLPath::Combine.md)|Cette fonction est un wrapper surchargé pour [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).|  
|[ATLPath::CommonPrefix](../Topic/ATLPath::CommonPrefix.md)|Cette fonction est un wrapper surchargé pour [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).|  
|[ATLPath::CompactPath](../Topic/ATLPath::CompactPath.md)|Cette fonction est un wrapper surchargé pour [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).|  
|[ATLPath::CompactPathEx](../Topic/ATLPath::CompactPathEx.md)|Cette fonction est un wrapper surchargé pour [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).|  
|[ATLPath::FileExists](../Topic/ATLPath::FileExists.md)|Cette fonction est un wrapper surchargé pour [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).|  
|[ATLPath::FindExtension](../Topic/ATLPath::FindExtension.md)|Cette fonction est un wrapper surchargé pour [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).|  
|[ATLPath::FindFileName](../Topic/ATLPath::FindFileName.md)|Cette fonction est un wrapper surchargé pour [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).|  
|[ATLPath::GetDriveNumber](../Topic/ATLPath::GetDriveNumber.md)|Cette fonction est un wrapper surchargé pour [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).|  
|[ATLPath::IsDirectory](../Topic/ATLPath::IsDirectory.md)|Cette fonction est un wrapper surchargé pour [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).|  
|[ATLPath::IsFileSpec](../Topic/ATLPath::IsFileSpec.md)|Cette fonction est un wrapper surchargé pour [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).|  
|[ATLPath::IsPrefix](../Topic/ATLPath::IsPrefix.md)|Cette fonction est un wrapper surchargé pour [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).|  
|[ATLPath::IsRelative](../Topic/ATLPath::IsRelative.md)|Cette fonction est un wrapper surchargé pour [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).|  
|[ATLPath::IsRoot](../Topic/ATLPath::IsRoot.md)|Cette fonction est un wrapper surchargé pour [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).|  
|[ATLPath::IsSameRoot](../Topic/ATLPath::IsSameRoot.md)|Cette fonction est un wrapper surchargé pour [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).|  
|[ATLPath::IsUNC](../Topic/ATLPath::IsUNC.md)|Cette fonction est un wrapper surchargé pour [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).|  
|[ATLPath::IsUNCServer](../Topic/ATLPath::IsUNCServer.md)|Cette fonction est un wrapper surchargé pour [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).|  
|[ATLPath::IsUNCServerShare](../Topic/ATLPath::IsUNCServerShare.md)|Cette fonction est un wrapper surchargé pour [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).|  
|[ATLPath::MakePretty](../Topic/ATLPath::MakePretty.md)|Cette fonction est un wrapper surchargé pour [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).|  
|[ATLPath::MatchSpec](../Topic/ATLPath::MatchSpec.md)|Cette fonction est un wrapper surchargé pour [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).|  
|[ATLPath::QuoteSpaces](../Topic/ATLPath::QuoteSpaces.md)|Cette fonction est un wrapper surchargé pour [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).|  
|[ATLPath::RelativePathTo](../Topic/ATLPath::RelativePathTo.md)|Cette fonction est un wrapper surchargé pour [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).|  
|[ATLPath::RemoveArgs](../Topic/ATLPath::RemoveArgs.md)|Cette fonction est un wrapper surchargé pour [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).|  
|[ATLPath::RemoveBackslash](../Topic/ATLPath::RemoveBackslash.md)|Cette fonction est un wrapper surchargé pour [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).|  
|[ATLPath::RemoveBlanks](../Topic/ATLPath::RemoveBlanks.md)|Cette fonction est un wrapper surchargé pour [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).|  
|[ATLPath::RemoveExtension](../Topic/ATLPath::RemoveExtension.md)|Cette fonction est un wrapper surchargé pour [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).|  
|[ATLPath::RemoveFileSpec](../Topic/ATLPath::RemoveFileSpec.md)|Cette fonction est un wrapper surchargé pour [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).|  
|[ATLPath::RenameExtension](../Topic/ATLPath::RenameExtension.md)|Cette fonction est un wrapper surchargé pour [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).|  
|[ATLPath::SkipRoot](../Topic/ATLPath::SkipRoot.md)|Cette fonction est un wrapper surchargé pour [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).|  
|[ATLPath::StripPath](../Topic/ATLPath::StripPath.md)|Cette fonction est un wrapper surchargé pour [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).|  
|[ATLPath::StripToRoot](../Topic/ATLPath::StripToRoot.md)|Cette fonction est un wrapper surchargé pour [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).|  
|[ATLPath::UnquoteSpaces](../Topic/ATLPath::UnquoteSpaces.md)|Cette fonction est un wrapper surchargé pour [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).|  
  
### Macros  
  
|||  
|-|-|  
|[Balises d'ATL\_URL](../Topic/ATL_URL%20Flags.md)|Ces indicateurs modifient le comportement d' [AtlEscapeUrl](../Topic/AtlEscapeUrl.md) et d' [AtlCanonicalizeUrl](../Topic/AtlCanonicalizeUrl.md) .|  
|[ATL\_WORKER\_THREAD\_WAIT](../Topic/ATL_WORKER_THREAD_WAIT.md)|Cette macro définit la valeur par défaut en millisecondes que [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md) attendra le thread de travail pour désactiver.|  
|[ATLS\_DEFAULT\_THREADPOOLSHUTDOWNTIMEOUT](../Topic/ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT.md)|Cette macro définit le temps par défaut en millisecondes que [CThreadPool](../atl/reference/cthreadpool-class.md) attend un thread s'arrête.|  
|[ATLS\_DEFAULT\_THREADSPERPROC](../Topic/ATLS_DEFAULT_THREADSPERPROC.md)|Cette macro définit le nombre par défaut de threads par processeur utilisé par [CThreadPool](../atl/reference/cthreadpool-class.md).|  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)