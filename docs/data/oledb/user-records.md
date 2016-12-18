---
title: "Enregistrements utilisateur | Microsoft Docs"
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
  - "COLUMN_ENTRY_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accesseurs (C++), jeux de lignes"
  - "accesseurs (C++), statiques"
  - "BEGIN_ACCESSOR (macro), exemple"
  - "BEGIN_ACCESSOR_MAP (macro)"
  - "CAccessor (classe), exemple"
  - "COLUMN_ENTRY (macro)"
  - "COLUMN_ENTRY_MAP (macro)"
  - "OLE DB (modèles du consommateur), enregistrements utilisateur"
  - "jeux de lignes (C++), accesseurs"
  - "enregistrements utilisateur, OLE DB (modèles du consommateur)"
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Enregistrements utilisateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour utiliser un accesseur statique, c'est\-à\-dire un accesseur dérivé de la classe **CAccessor**, le consommateur doit disposer d'un enregistrement utilisateur.  L'enregistrement utilisateur est une classe C\+\+ qui contient des éléments de données pour gérer les entrées et les sorties.  L'Assistant Consommateur OLE DB ATL génère un enregistrement utilisateur pour le consommateur.  Vous pouvez ajouter des méthodes à l'enregistrement utilisateur pour des tâches facultatives telles que la gestion des commandes.  
  
 Le code ci\-après montre un exemple d'enregistrement qui gère les commandes.  Dans l'enregistrement d'utilisateur, `BEGIN_COLUMN_MAP` représente un ensemble de lignes de données passées au consommateur par un fournisseur.  `BEGIN_PARAM_MAP` représente un jeu de paramètres de commande.  Cet exemple utilise une classe [CCommand](../../data/oledb/ccommand-class.md) pour gérer les paramètres des commandes.  Les données membres dans les entrées de mappage représentent des offsets dans un seul bloc contigu de la mémoire pour chaque instance de la classe.  Les macros `COLUMN_ENTRY` correspondent aux macros `PROVIDER_COLUMN_ENTRY` côté fournisseur.  
  
 Pour plus d'informations sur les macros **COLUMN\_MAP** et **PARAM\_MAP**, consultez [Macros pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## Enregistrements utilisateur générés par l'Assistant  
 Si vous utilisez l'Assistant Consommateur OLE DB ATL pour générer un consommateur, vous aurez le choix entre les options Modèles OLE DB et Attributs OLE DB.  Le code généré diffère à chaque fois.  Pour plus d'informations sur ce code, consultez [Classes de consommateur générées par l'Assistant](../../data/oledb/consumer-wizard-generated-classes.md).  
  
## Prise en charge d'accesseurs multiples par des enregistrements utilisateur  
 Pour une description complète des scénarios dans lesquels vous devez utiliser plusieurs accesseurs, consultez [Utilisation de plusieurs accesseurs dans un jeu de lignes](../../data/oledb/using-multiple-accessors-on-a-rowset.md).  
  
 L'exemple suivant montre l'enregistrement utilisateur modifié pour prendre en charge plusieurs accesseurs sur le jeu de lignes.  À la place de `BEGIN_COLUMN_MAP` et de `END_COLUMN_MAP`, il utilise [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md) et [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) pour chaque accesseur.  La macro `BEGIN_ACCESSOR` spécifie le numéro de l'accesseur \(offset à partir de zéro\) et indique si l'accesseur est un auto\-accesseur.  Les auto\-accesseurs appellent `GetData` pour récupérer les données automatiquement via un appel à [MoveNext](../../data/oledb/crowset-movenext.md).  Les accesseurs non automatiques exigent une récupération explicite des données.  Utilisez un accesseur non automatique si vous établissez une liaison avec un vaste champ de données \(une image bitmap, par exemple\) que vous ne souhaitez peut\-être pas récupérer pour chaque enregistrement.  
  
```  
class CMultiArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)  
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor  
    COLUMN_ENTRY(1, m_szFirstName)  
    COLUMN_ENTRY(2, m_szLastName)  
   END_ACCESSOR()  
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor  
    COLUMN_ENTRY(3, m_nAge)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)