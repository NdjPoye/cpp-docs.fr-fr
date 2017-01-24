---
title: "CArchive Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class"
  - "data storage [C++], CArchive class"
  - "I/O [MFC], archiving objects"
  - "sérialisation (C++), CArchive class"
  - "storage [C++], CArchive class"
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArchive Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet d'enregistrer un réseau complexe des objets dans un formulaire binaire permanente \(généralement stockage disque\) qui rend une fois ces objets sont supprimés.  
  
## Syntaxe  
  
```  
class CArchive  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CArchive::CArchive](../Topic/CArchive::CArchive.md)|Crée un objet `CArchive`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CArchive::Abort](../Topic/CArchive::Abort.md)|Ferme une archive sans lever une exception.|  
|[CArchive::Close](../Topic/CArchive::Close.md)|Vide des données et des déconnectez \-vous pas écrits d' `CFile`.|  
|[CArchive::Flush](../Topic/CArchive::Flush.md)|Vide des données non entrées de la mémoire tampon d'archivage.|  
|[CArchive::GetFile](../Topic/CArchive::GetFile.md)|Obtient le pointeur d'objet d' `CFile` pour cette archive.|  
|[CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md)|Appel de la fonction d' `Serialize` pour déterminer la version de l'objet qui est désérialisé.|  
|[CArchive::IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md)|Détermine si la mémoire tampon a été vidée lors de Windows Sockets acceptent le processus.|  
|[CArchive::IsLoading](../Topic/CArchive::IsLoading.md)|Détermine si l'archive charge.|  
|[CArchive::IsStoring](../Topic/CArchive::IsStoring.md)|Détermine si l'archive enregistrées.|  
|[CArchive::MapObject](../Topic/CArchive::MapObject.md)|Définit les objets de la carte qui ne sont pas sérialisés au fichier, mais qui sont disponibles pour les sous\-objets référence.|  
|[CArchive::Read](../Topic/CArchive::Read.md)|Lit les octets bruts.|  
|[CArchive::ReadClass](../Topic/CArchive::ReadClass.md)|Lit une référence de classe précédemment enregistrée avec `WriteClass`.|  
|[CArchive::ReadObject](../Topic/CArchive::ReadObject.md)|Appelle la fonction d' `Serialize` d'un objet pour charger.|  
|[CArchive::ReadString](../Topic/CArchive::ReadString.md)|Lit une ligne de texte.|  
|[CArchive::SerializeClass](../Topic/CArchive::SerializeClass.md)|Lit ou écrit la référence de classe à l'objet d' `CArchive` selon la direction d' `CArchive`.|  
|[CArchive::SetLoadParams](../Topic/CArchive::SetLoadParams.md)|Définit la taille à laquelle le tableau de charge augmente.  Doit être appelé avant tout objet soit chargé ou avant `MapObject` ou `ReadObject` est appelé.|  
|[CArchive::SetObjectSchema](../Topic/CArchive::SetObjectSchema.md)|Définit le schéma d'objet stocké dans l'objet archive.|  
|[CArchive::SetStoreParams](../Topic/CArchive::SetStoreParams.md)|Définit la taille de table de hachage et la taille des blocs de mappage utilisée pour identifier de seuls objets pendant le processus de sérialisation.|  
|[CArchive::Write](../Topic/CArchive::Write.md)|Écrit des octets bruts.|  
|[CArchive::WriteClass](../Topic/CArchive::WriteClass.md)|Écrit une référence à `CRuntimeClass` à `CArchive`.|  
|[CArchive::WriteObject](../Topic/CArchive::WriteObject.md)|Appelle la fonction d' `Serialize` d'un objet pour stocker.|  
|[CArchive::WriteString](../Topic/CArchive::WriteString.md)|Écrit une ligne de texte.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)|Objets et types primitifs de mémoire à l'archivage.|  
|[CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)|Objets et types primitifs de chargement de l'archive.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CArchive::m\_pDocument](../Topic/CArchive::m_pDocument.md)||  
  
## Notes  
 `CArchive` n'a pas de classe de base.  
  
 Plus loin vous pouvez charger les objets de stockage permanent, les reconstituant dans la mémoire.  Ce processus de rendre les données persistantes est appelé « sérialisation. »  
  
 Vous pouvez considérer un objet archive comme type de flux binaire.  Comme un flux d'entrée\/sortie, une archive est associée à un fichier et permet l'écriture et la lecture des données mises en mémoire tampon vers et à partir de la mémoire.  Les séquences de processus à partir d'un flux d'entrée\/sortie de caractères ASCII, mais une archive traite des données binaires d'objet dans un format efficace et nonredundant.  
  
 Vous devez créer un objet de [fichier C](../../mfc/reference/cfile-class.md) avant de pouvoir créer un objet d' `CArchive` .  De plus, vous devez vérifier que le mode de chargement\/mémoire de l'archive est compatible avec le mode ouverture du fichier.  Vous êtes limité à une archive active par fichier.  
  
 Lorsque vous construisez un objet d' `CArchive` , vous le liez à un objet de la classe `CFile` \(ou une classe dérivée\) qui représente un fichier ouvert.  Vous spécifiez également si l'archive sera utilisée pour charger ou enregistrer.  Un objet d' `CArchive` peut traiter non seulement des types primitifs mais également des objets de [CObject](../../mfc/reference/cobject-class.md)\- classes dérivées conçues pour la sérialisation.  Une classe sérialisable a généralement une fonction membre d' `Serialize` , et elle utilise généralement les macros de [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) et d' [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) , comme décrit dans la classe `CObject`.  
  
 L'extraction surchargée \(**\>\>**\) et \(\)**\<\<**les opérateurs d'insertion sont des interfaces de programmation pratiques d'archivage qui prennent en charge les types primitifs et `CObject`\- classes dérivées.  
  
 `CArchive` prend également en charge la programmation avec les classes [CSocket](../../mfc/reference/csocket-class.md) et [CSocketFile](../../mfc/reference/csocketfile-class.md)de MFC Windows Sockets.  Prend en charge de fonction membre d' [IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md) qui utilisent.  
  
 Pour plus d'informations sur `CArchive`, consultez les articles [sérialisation](../../mfc/serialization-in-mfc.md) et [Windows Sockets : Utilisation des sockets avec des archives](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## Hiérarchie d'héritage  
 `CArchive`  
  
## Configuration requise  
 **Header:** afx.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)