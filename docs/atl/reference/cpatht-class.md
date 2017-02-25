---
title: "CPathT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPathT"
  - "CPathT"
  - "ATL::CPathT<StringType>"
  - "ATL::CPathT"
  - "ATL.CPathT<StringType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPathT class"
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CPathT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un chemin d'accès.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template< typename   
      StringType  
      >   
class CPathT  
```  
  
#### Paramètres  
 `StringType`  
 La classe de chaîne ATL\/MFC à utiliser pour le chemin d'accès \(consultez [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)\).  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPathT::PCXSTR](../Topic/CPathT::PCXSTR.md)|Un type chaîne constante.|  
|[CPathT::PXSTR](../Topic/CPathT::PXSTR.md)|Un type chaîne.|  
|[CPathT::XCHAR](../Topic/CPathT::XCHAR.md)|Type caractère|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPathT::CPathT](../Topic/CPathT::CPathT.md)|Le constructeur pour le chemin d'accès.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPathT::AddBackslash](../Topic/CPathT::AddBackslash.md)|Appelez cette méthode pour ajouter une barre oblique inverse à la fin d'une chaîne pour créer la syntaxe correcte pour un chemin d'accès.|  
|[CPathT::AddExtension](../Topic/CPathT::AddExtension.md)|Appelez cette méthode pour ajouter une extension de fichier à un tracé.|  
|[CPathT::Append](../Topic/CPathT::Append.md)|Appelez cette méthode pour ajouter une chaîne au chemin d'accès actuel.|  
|[CPathT::BuildRoot](../Topic/CPathT::BuildRoot.md)|Appelez cette méthode pour créer un chemin d'accès racine d'un nombre donné de lecteur.|  
|[CPathT::Canonicalize](../Topic/CPathT::Canonicalize.md)|Appelez cette méthode pour convertir le chemin d'accès au formulaire canonique.|  
|[CPathT::Combine](../Topic/CPathT::Combine.md)|Appelez cette méthode pour concaténer une chaîne représentant un nom de dossier et une chaîne représentant un nom de chemin d'accès de fichier dans un chemin d'accès.|  
|[CPathT::CommonPrefix](../Topic/CPathT::CommonPrefix.md)|Appelez cette méthode pour déterminer si le chemin d'accès spécifié partage un préfixe commun avec le chemin d'accès actuel.|  
|[CPathT::CompactPath](../Topic/CPathT::CompactPath.md)|Appelez cette méthode pour tronquer un chemin d'accès pour entrer dans une largeur données de pixels en remplaçant les composants de chemin d'accès par des points de suspension.|  
|[CPathT::CompactPathEx](../Topic/CPathT::CompactPathEx.md)|Appelez cette méthode pour tronquer un chemin d'accès pour entrer dans un nombre spécifié de caractères en remplaçant les composants de chemin d'accès par des points de suspension.|  
|[CPathT::FileExists](../Topic/CPathT::FileExists.md)|Appelez cette méthode pour vérifier si le fichier à ce chemin d'accès existe.|  
|[CPathT::FindExtension](../Topic/CPathT::FindExtension.md)|Appelez cette méthode pour rechercher la position de l'extension de fichier dans le chemin d'accès.|  
|[CPathT::FindFileName](../Topic/CPathT::FindFileName.md)|Appelez cette méthode pour rechercher la position du nom de fichier dans le chemin d'accès.|  
|[CPathT::GetDriveNumber](../Topic/CPathT::GetDriveNumber.md)|Appelez cette méthode pour rechercher le chemin d'accès à une lettre de lecteur dans la plage « A » à « Z » et retourner le nombre correspondant de lecteur.|  
|[CPathT::GetExtension](../Topic/CPathT::GetExtension.md)|Appelez cette méthode pour obtenir l'extension de fichier du tracé.|  
|[CPathT::IsDirectory](../Topic/CPathT::IsDirectory.md)|Appelez cette méthode pour vérifier si le chemin d'accès est un répertoire valide.|  
|[CPathT::IsFileSpec](../Topic/CPathT::IsFileSpec.md)|Appelez cette méthode pour rechercher un chemin d'accès pour tous les caractères chemin\- les délimitant \(par exemple, « :  » ou « \\ "\).  S'il n'existe aucun caractère chemin\- le délimitant actuel, le chemin est considéré comme un chemin de spécification de fichier.|  
|[CPathT::IsPrefix](../Topic/CPathT::IsPrefix.md)|Appelez cette méthode pour déterminer si un chemin d'accès contient un préfixe valide du type passé par `pszPrefix`.|  
|[CPathT::IsRelative](../Topic/CPathT::IsRelative.md)|Appelez cette méthode pour déterminer si le chemin d'accès est associé.|  
|[CPathT::IsRoot](../Topic/CPathT::IsRoot.md)|Appelez cette méthode pour déterminer si le chemin d'accès est une racine du dossier.|  
|[CPathT::IsSameRoot](../Topic/CPathT::IsSameRoot.md)|Appelez cette méthode pour déterminer si un autre chemin a un composant racine commun avec le chemin d'accès actuel.|  
|[CPathT::IsUNC](../Topic/CPathT::IsUNC.md)|Appelez cette méthode pour déterminer si le chemin d'accès est un chemin UNC valide \(convention d'affectation de noms\) pour un serveur et un partage.|  
|[CPathT::IsUNCServer](../Topic/CPathT::IsUNCServer.md)|Appelez cette méthode pour déterminer si le chemin d'accès est un chemin UNC valide \(convention d'affectation de noms\) pour un serveur uniquement.|  
|[CPathT::IsUNCServerShare](../Topic/CPathT::IsUNCServerShare.md)|Appelez cette méthode pour déterminer si le chemin d'accès est un chemin d'accès valide de partage UNC \(convention d'affectation de noms\), \\\\*server*\\*partage*.|  
|[CPathT::MakePretty](../Topic/CPathT::MakePretty.md)|Appelez cette méthode pour convertir un chemin d'accès à toutes les lettres minuscules pour donner au chemin une apparence cohérente.|  
|[CPathT::MatchSpec](../Topic/CPathT::MatchSpec.md)|Appelez cette méthode pour rechercher le chemin d'accès à une chaîne contenant un type générique de correspondance.|  
|[CPathT::QuoteSpaces](../Topic/CPathT::QuoteSpaces.md)|Appelez cette méthode pour placer le chemin d'accès entre guillemets s'il contient des espaces.|  
|[CPathT::RelativePathTo](../Topic/CPathT::RelativePathTo.md)|Appelez cette méthode pour créer un chemin d'accès relatif d'un fichier ou dossier à un autre.|  
|[CPathT::RemoveArgs](../Topic/CPathT::RemoveArgs.md)|Appelez cette méthode pour supprimer tous les arguments de ligne de commande du tracé.|  
|[CPathT::RemoveBackslash](../Topic/CPathT::RemoveBackslash.md)|Appelez cette méthode pour supprimer la barre oblique inverse finale du chemin d'accès.|  
|[CPathT::RemoveBlanks](../Topic/CPathT::RemoveBlanks.md)|Appelez cette méthode pour supprimer tous les espaces à gauche et à droite du tracé.|  
|[CPathT::RemoveExtension](../Topic/CPathT::RemoveExtension.md)|Appelez cette méthode pour supprimer l'extension de fichier du chemin d'accès, le cas échéant.|  
|[CPathT::RemoveFileSpec](../Topic/CPathT::RemoveFileSpec.md)|Appelez cette méthode pour supprimer le nom de fichier et la barre oblique inverse finale du chemin d'accès, s'il a.|  
|[CPathT::RenameExtension](../Topic/CPathT::RenameExtension.md)|Appelez cette méthode pour remplacer l'extension de nom de fichier dans le chemin d'accès par une nouvelle extension.  Si le nom de fichier ne contient pas d'extension, l'extension est attachée à la fin de la chaîne.|  
|[CPathT::SkipRoot](../Topic/CPathT::SkipRoot.md)|Appelez cette méthode pour analyser un chemin d'accès, en ignorant la lettre de lecteur ou le serveur UNC\/partage de composants de chemin d'accès.|  
|[CPathT::StripPath](../Topic/CPathT::StripPath.md)|Appelez cette méthode pour supprimer la partie du chemin d'accès d'un chemin qualifié complet et un nom de fichier.|  
|[CPathT::StripToRoot](../Topic/CPathT::StripToRoot.md)|Appelez cette méthode pour supprimer tous les éléments du chemin d'accès à l'exception de les informations racine.|  
|[CPathT::UnquoteSpaces](../Topic/CPathT::UnquoteSpaces.md)|Appelez cette méthode pour supprimer des guillemets le début et la fin d'un tracé.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPathT::operator const StringType &](../Topic/CPathT::operator%20const%20StringType%20&.md)|Cet opérateur permet l'objet à traiter comme une chaîne.|  
|[CPathT::operator CPathT::PCXSTR](../Topic/CPathT::operator%20CPathT::PCXSTR.md)|Cet opérateur permet l'objet à traiter comme une chaîne.|  
|[CPathT::operator StringType &](../Topic/CPathT::operator%20StringType%20&.md)|Cet opérateur permet l'objet à traiter comme une chaîne.|  
|[CPathT::operator \+\=](../Topic/CPathT::operator%20+=.md)|Cet opérateur ajoute une chaîne au chemin d'accès.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPathT::m\_strPath](../Topic/CPathT::m_strPath.md)|Chemin d'accès.|  
  
## Notes  
 `CPath`, `CPathA`, et `CPathW` sont des instanciations de `CPathT` définie comme suit :  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## Configuration requise  
 **Header:** atlpath.h  
  
## Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)   
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)