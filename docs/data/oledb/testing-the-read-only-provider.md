---
title: "Test du fournisseur accessible en lecture seule | Microsoft Docs"
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
  - "fournisseurs OLE DB, appeler"
  - "fournisseurs OLE DB, tester"
  - "tester les fournisseurs"
  - "tester, fournisseurs OLE DB"
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Test du fournisseur accessible en lecture seule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour tester un fournisseur, vous avez besoin d'un consommateur.  Si le consommateur correspond au fournisseur, c'est encore mieux.  Les modèles du consommateur OLE DB constituent une fine couche qui enveloppe OLE DB et correspondent aux objets COM du fournisseur.  Dans la mesure où la source est livrée avec les modèles du consommateur, il est facile de déboguer un fournisseur par leur intermédiaire.  Les modèles du consommateur offrent également un moyen très simple et rapide de développement d'applications consommateur.  
  
 L'exemple utilisé dans cette rubrique crée une application Assistant Application MFC pour un consommateur de test.  L'application de test est une simple boîte de dialogue incorporant un code de modèle du consommateur OLE DB.  
  
### Pour créer l'application de test  
  
1.  Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet**.  
  
2.  Dans le volet Types de projets, sélectionnez le dossier **Projets Visual C\+\+**.  Dans le volet Modèles, cliquez sur **Application MFC**.  
  
3.  Pour le nom de projet, entrez **TestProv** et cliquez sur **OK**.  
  
     L'Assistant Application MFC apparaît.  
  
4.  Dans la page **Type d'application**, sélectionnez **Basée sur des boîtes de dialogue**.  
  
5.  Dans la page **Fonctionnalités avancées**, sélectionnez **Automation**, puis cliquez sur **Terminer**.  
  
> [!NOTE]
>  L'application ne requiert pas la prise en charge d'Automation si vous ajoutez **CoInitialize** dans **CTestProvApp::InitInstance**.  
  
 Vous pouvez afficher et modifier la boîte de dialogue TestProv \(IDD\_TESTPROV\_DIALOG\) en la sélectionnant dans l'Affichage des ressources.  Placez deux zones de liste, une pour chaque chaîne dans le jeu de lignes, dans la boîte de dialogue.  Désactivez la propriété de tri pour les deux zones de liste en appuyant sur ALT\+Entrée après avoir sélectionné une zone de liste, puis cliquez sur l'onglet **Styles** et désactivez la case à cocher **Trier**.  Placez également un bouton **Exécuter** dans la boîte de dialogue pour l'extraction du fichier.  La boîte de dialogue TestProv terminée doit contenir deux zones de liste intitulées « String 1 » et « String 2 », respectivement ; elle doit également contenir des boutons **OK**, **Annuler** et **Exécuter**.  
  
 Ouvrez le fichier d'en\-tête pour la classe de boîte de dialogue \(en l'occurrence TestProvDlg.h\).  Ajoutez le code suivant au fichier d'en\-tête \(en dehors de toute déclaration de classe\) :  
  
```  
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
 Le code représente un enregistrement utilisateur qui définit les colonnes qui figureront dans le jeu de lignes.  Quand le client appelle **IAccessor::CreateAccessor**, il utilise ces entrées pour spécifier les colonnes à lier.  Les modèles du consommateur OLE DB permettent également de lier les colonnes de manière dynamique.  Les macros COLUMN\_ENTRY sont la version côté client des macros PROVIDER\_COLUMN\_ENTRY.  Les deux macros COLUMN\_ENTRY spécifient l'ordinal, le type, la longueur et les données membres pour les deux chaînes.  
  
 Ajoutez une fonction gestionnaire pour le bouton **Exécuter** en appuyant sur CTRL et en double\-cliquant sur le bouton **Exécuter**.  Ajoutez le code suivant à la fonction :  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
 Les classes `CCommand`, `CDataSource` et `CSession` appartiennent toutes aux modèles du consommateur OLE DB.  Chaque classe simule un objet COM dans le fournisseur.  L'objet `CCommand` prend la classe `CProvider`, déclarée dans le fichier d'en\-tête, en tant que paramètre de modèle.  Le paramètre `CProvider` représente les liaisons que vous utilisez pour accéder aux données à partir du fournisseur.  Voici le code `Open` pour la source de données, la session et la commande :  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 Les lignes permettant d'ouvrir les classes créent chaque objet dans le fournisseur.  Pour retrouver le fournisseur, utilisez le ProgID du fournisseur.  Vous pouvez obtenir le ProgID à partir de la base de registres ou en consultant le fichier MyProvider.rgs \(ouvrez le répertoire du fournisseur et recherchez la clé ProgID\).  
  
 Le fichier MyData.txt est inclus dans l'exemple MyProv.  Pour créer un fichier qui vous est propre, utilisez un éditeur et tapez un nombre pair de chaînes, en appuyant sur ENTRÉE entre chaque chaîne.  Modifiez le nom du chemin si vous déplacez le fichier.  
  
 Passez la chaîne « c:\\\\samples\\\\myprov\\\\MyData.txt » dans la ligne `table.Open`.  Si vous exécutez pas à pas l'appel `Open`, vous pouvez voir que cette chaîne est passée à la méthode `SetCommandText` dans le fournisseur.  Remarquez que la méthode `ICommandText::Execute` a utilisé cette chaîne.  
  
 Pour obtenir les données, appelez `MoveNext` dans la table.  `MoveNext` appelle les fonctions **IRowset::GetNextRows**, `GetRowCount` et `GetData`.  Quand il ne reste plus de lignes \(autrement dit, la position en cours dans le jeu de lignes est supérieure à `GetRowCount`\), la boucle se termine :  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 Notez que lorsqu'il ne reste plus de lignes, les fournisseurs retournent **DB\_S\_ENDOFROWSET**.  La valeur **DB\_S\_ENDOFROWSET** n'est pas une erreur.  Vous devez toujours procéder à une vérification par rapport à `S_OK` pour annuler une boucle d'extraction de données et ne pas utiliser la macro SUCCEEDED.  
  
 Vous devez à présent pouvoir générer et tester le programme.  
  
## Voir aussi  
 [Amélioration du fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md)