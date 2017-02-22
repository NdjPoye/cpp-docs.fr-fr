---
title: "TN002&#160;: format des donn&#233;es d&#39;objets persistants | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive (classe), prise en charge des données persistantes"
  - "objets C++ persistants"
  - "données d'objets persistants"
  - "TN002"
  - "VERSIONABLE_SCHEMA (macro)"
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# TN002&#160;: format des donn&#233;es d&#39;objets persistants
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit les routines de MFC qui prennent en charge les objets persistants C\+\+ et le format des données d'objet lorsqu'il est stocké dans un fichier.  Cette section s'applique uniquement aux classes avec les macros [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) et [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md).  
  
## Le problème  
 L'implémentation MFC de données persistantes stocke des données pour de nombreux objets à une seule partie contiguës de fichier.  La méthode de l'objet `Serialize` traduit les données de l'objet dans un format binaire compact.  
  
 L'implémentation s'assure que toutes les données sont stockées dans le même format à l'aide de [CArchive Class](../mfc/reference/carchive-class.md).  Elle utilise un objet `CArchive` comme traducteur.  Cet objet est conservé depuis le moment où il est créé jusqu'à ce que vous appeliez [CArchive::Close](../Topic/CArchive::Close.md).  Cette méthode peut être appelée explicitement par le programmeur ou implicitement par le destructeur lorsque le programme quitte le champ qui contient `CArchive`.  
  
 Cette remarque décrit l'implémentation des membres [CArchive::ReadObject](../Topic/CArchive::ReadObject.md) [CArchive::WriteObject](../Topic/CArchive::WriteObject.md)et`CArchive`.  Vous trouverez le code pour ces fonctions dans Arcobj.cpp, et l'implémentation clé de `CArchive` dans Arccore.cpp.  Le code utilisateur n'appelle pas `ReadObject` et `WriteObject` directement.  À la place, ces objets sont utilisés par insertion de type sécurisé et opérateurs d'extraction de classe spécifique qui sont générés automatiquement par les macros `DECLARE_SERIAL` et `IMPLEMENT_SERIAL`.  Le code suivant montre comment `WriteObject` et `ReadObject` sont implicitement appelé :  
  
```  
class CMyObject : public CObject  
{  
    DECLARE_SERIAL(CMyObject)  
};  
  
IMPLEMENT_SERIAL(CMyObj, CObject, 1)  
  
// example usage (ar is a CArchive&)  
CMyObject* pObj;  
CArchive& ar;  
ar << pObj;        // calls ar.WriteObject(pObj)  
ar >> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))  
```  
  
## Enregistrements d'objets dans le magasin \(CArchive::WriteObject\)  
 La méthode `CArchive::WriteObject` écrit des données d'en\-tête qui sont utilisées pour reconstruire l'objet.  Ces données comprennent deux parties : le type de l'objet et l'état de l'objet.  Cette méthode est également chargée de gérer l'identité de l'objet qui est rentré, afin qu'une seule copie soit enregistrée, quel que soit le nombre de pointeurs sur cet objet \(pointeurs circulaires compris\).  
  
 Enregistrer \(insérer\) et restaurer \(extraction\) des objets s'appuie sur plusieurs « constantes manifestes. » Ce sont les valeurs stockées dans les types binaires et fournissant des informations importantes à l'archive \(notez que le préfixe « W » affiche les quantités 16 bits\) :  
  
|Tag|Description|  
|---------|-----------------|  
|wNullTag|Utilisé pour les pointeurs \(0\) d'objets NULL.|  
|wNewClassTag|Indique à la description de la classe que les suivantes sont nouvelles dans ce contexte d'archive \(\- 1\).|  
|wOldClassTag|Indique que la classe de l'objet en cours de lecture a été détectée dans ce contexte \(0x8000\).|  
  
 En enregistrant des objets, l'archive maintient un [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) \( `m_pStoreMap`\) qui est le mappage d'un objet stocké à un identificateur persistant 32 bits \(PID\).  Un PID est affecté à chaque objet unique et chaque nom unique de la classe qui est enregistré dans le contexte de l'archivage.  Ces PIDs sont distribués séquentiellement à partir de 1.  Ces PIDs n'ont aucune importance en dehors de l'archivage et, en particulier, ne doivent pas être confondus avec des nombres d'enregistrement ou d'autres éléments d'identité.  
  
 Dans la classe `CArchive`, les PIDs sont de 32 bits, mais ils sont enregistrés comme 16 bits à moins d'être supérieure à 0x7FFE.  Des PIDs sont écrits en tant que 0x7FFF suivi PID 32 bits.  Cela maintient la compatibilité avec les projets créés dans des versions antérieures.  
  
 Lorsqu'une demande est effectuée pour enregistrer un objet dans une archive \(généralement à l'aide de l'opérateur insert global\), une vérification est effectuée pour un pointeur d'un [CObject](../mfc/reference/cobject-class.md) NULL.  Si le pointeur est NULL, `wNullTag` est inséré dans le flux de données d'archive.  
  
 Si le pointeur n'est pas NULL et peut être sérialisé \(la classe est une classe `DECLARE_SERIAL` \), les contrôles de code `m_pStoreMap` pour voir si l'objet a déjà été inscrit.  S'il en a, le code insère le PID 32 bits associé à cet objet dans un flux de données d'archive.  
  
 Si l'objet n'a pas été enregistré précédemment, il existe deux possibilités à considérer : soit l'objet et le type exact \(autrement dit, classe\) de l'objet sont nouveaux dans ce contexte d'archive, soit l'objet est un type exact déjà affiché.  Pour déterminer si le type a été détecté, le code fait la requête de `m_pStoreMap` pour un objet [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) qui correspond à l'objet `CRuntimeClass` associé à l'objet en cours d'enregistrement.  S'il existe une correspondance, `WriteObject` insère un indicateur qui comporte le même nombre `OR` de bits que `wOldClassTag` et que cet index.  Si `CRuntimeClass` est nouveau dans ce contexte d'archive, `WriteObject` affecte un nouveau PID à cette classe et l'insère dans l'archive, précédée par la valeur `wNewClassTag`.  
  
 Le descripteur de cette classe est alors inséré dans l'archive à l'aide de la méthode `CRuntimeClass::Store`.  `CRuntimeClass::Store` insère le numéro du schéma de la classe \(voir ci\-dessous\) et le nom de texte ASCII de la classe.  Notez que l'utilisation du nom ASCII de texte ne garantit pas l'unicité de archive entre les applications.  Par conséquent, vous devez référencer vos fichiers de données pour empêcher l'altération.  Après l'insertion des informations de classe, l'archive place l'objet dans `m_pStoreMap` puis appelle la méthode `Serialize` pour insérer des données de classe spécifique.  Placer l'objet dans `m_pStoreMap` avant d'appeler `Serialize` empêche plusieurs copies de l'objet d'être stocké dans le magasin.  
  
 Lors du retour de l'appel initial \(généralement la racine du réseau des objets\), vous devez appeler [CArchive::Close](../Topic/CArchive::Close.md).  Si vous envisagez d'exécuter d'autres opérations [Fichier C](../mfc/reference/cfile-class.md), appelez la méthode [Vide](../Topic/CArchive::Flush.md) `CArchive` pour empêcher l'altération de l'archivage.  
  
> [!NOTE]
>  Cette implémentation impose une limite inconditionnelle des index 0x3FFFFFFE par contexte d'archive.  Ce nombre représente le nombre maximal des objets uniques et des classes qui peuvent être stockés dans une seule archive, mais un seul fichier de disque peut contenir un nombre illimité de contextes d'archive.  
  
## Chargement des objets à partir du magasin \(CArchive::ReadObject\)  
 Charger \(extraire\) des objets utilise la méthode `CArchive::ReadObject` et est l'inverse de `WriteObject`.  Comme `WriteObject`, `ReadObject` n'est pas appelé directement par le code utilisateur ; le code utilisateur doit appeler l'opérateur d'extraction de type sécurisé qui appelle `ReadObject` avec `CRuntimeClass`prévu.  Il assure l'intégrité du type de l'opération d'extraction.  
  
 Depuis l'implémentation `WriteObject` affecte des PIDs augmentant, en commençant par 1 \(0 est prédéfini comme objet NULL\), l'implémentation `ReadObject` peut utiliser une table pour gérer l'état du contexte d'archive.  Lorsque le PID est lu à partir du magasin, si le PID est supérieur à la limite actuelle supérieure de `m_pLoadArray`, `ReadObject` sait qu'un nouvel objet \(ou la description de la classe\) suit.  
  
## Nombre de schémas  
 Numéro de schéma, qui est affecté à cette classe lorsque la méthode `IMPLEMENT_SERIAL` de classe est produite, correspond à « version » de l'implémentation de la classe.  Le schéma fait référence à l'implémentation de la classe, pas au nombre d'occurrences d'un objet donné a été rendu persistant \(généralement appelé de la version de l'objet\).  
  
 Si vous envisagez de gérer différentes implémentations de la même classe avec le temps, incrémenter le schéma lors que vous modifiez l'implémentation de la méthode `Serialize` de votre objet permet d'écrire du code qui peut charger des objets stockés à l'aide de les versions antérieures de l'implémentation.  
  
 La méthode `CArchive::ReadObject` lèvera une [CArchiveException](../mfc/reference/carchiveexception-class.md) lorsqu'elle rencontre un nombre de schéma dans le magasin persistant qui est différent du nombre schéma de la description de la classe en mémoire.  Il n'est pas facile d'extraire à partir de cette exception.  
  
 Utilisez `VERSIONABLE_SCHEMA` combiné avec \( `OR`bits\) votre version du schéma pour empêcher cette exception d'être levée.  À l'aide de `VERSIONABLE_SCHEMA`, votre code peut prendre la mesure appropriée dans sa fonction `Serialize` en vérifiant la valeur de retour de [CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md).  
  
## Appeler directement la sérialisation  
 Dans de nombreux cas la charge du schéma général d'archive de `WriteObject` et de `ReadObject` n'est pas nécessaire.  C'est le cas courant de sérialiser les données dans un [CDocument](../mfc/reference/cdocument-class.md).  Dans ce cas, la méthode `Serialize` de `CDocument` est appelée directement, et non avec les opérateurs d'extraction ou d'insertion.  Le contenu du document peut ensuite utiliser le schéma plus général d'archive de l'objet.  
  
 Appeler `Serialize` directement les avantages et les inconvénients suivants :  
  
-   Aucun octet supplémentaire n'est ajouté à l'archive avant ou après la sérialisation de l'objet.  Cela rend non seulement les données stockées plus petites, mais vous permet d'implémenter les routines `Serialize` pouvant gérer tous les formats de fichier.  
  
-   MFC est analysé pour que les implémentations `WriteObject` et d'`ReadObject` et les collections associées ne sont pas liées dans votre application sauf si vous avez besoin du schéma plus générale d'archive d'un autre fonction.  
  
-   Votre code ne doit pas récupérer des nombres de schéma anciens.  Cela rend votre code de sérialisation de document chargé d'encoder les nombres de schéma, numéro de version du format de fichier, ou n'importe quel numéro d'identification que vous utilisez au début des fichiers de données.  
  
-   Un objet qui est sérialisé par un appel à un `Serialize` ne doit pas utiliser `CArchive::GetObjectSchema` ou doit gérer une valeur de retour \(UINT\) \- 1 indique que la version est inconnu.  
  
 Comme `Serialize` est appelé directement sur votre document, il n'est généralement pas possible pour les objets sub du document des références d'archive à leur élément parent.  Ces objets doivent obtenir un pointeur à son document conteneur explicitement ou vous devez utiliser la fonction [CArchive::MapObject](../Topic/CArchive::MapObject.md) pour mapper le pointeur d'`CDocument` à PID pour que ces pointeurs validées soient archivés.  
  
 Comme indiqué précédemment, vous devez encoder la version et les informations de classe lorsque vous appelez `Serialize` directement, ce qui vous permet de modifier le format ultérieurement tout en continuant à maintenir la compatibilité descendante avec les fichiers antérieurs.  La fonction `CArchive::SerializeClass` peut être appelée explicitement avant la sérialisation directe d'un objet ou avant d'appeler une classe de base.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)