---
title: "Comment&#160;: lire les donn&#233;es du Registre Windows (C++/CLI) | Microsoft Docs"
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
  - "Registre, lire"
  - "Visual C++, lire dans un registre Windows"
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: lire les donn&#233;es du Registre Windows (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant utilise la clé <xref:Microsoft.Win32.Registry.CurrentUser> pour lire les données du Registre Windows.  Les sous\-clé sont d'abord énumérées à l'aide de la méthode <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A>, puis la sous\-clé Identities est ouverte à l'aide de la méthode <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A>.  Comme les clés racine, chaque sous\-clé est représentée par la classe <xref:Microsoft.Win32.RegistryKey>.  Pour terminer, le nouvel objet <xref:Microsoft.Win32.RegistryKey> est utilisé pour énumérer les paires clé\/valeur.  
  
## Exemple  
  
### Code  
  
```  
// registry_read.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main( )  
{  
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );  
  
   Console::WriteLine("Subkeys within CurrentUser root key:");  
   for (int i=0; i<key->Length; i++)  
   {  
      Console::WriteLine("   {0}", key[i]);  
   }  
  
   Console::WriteLine("Opening subkey 'Identities'...");  
   RegistryKey^ rk = nullptr;  
   rk = Registry::CurrentUser->OpenSubKey("Identities");  
   if (rk==nullptr)  
   {  
      Console::WriteLine("Registry key not found - aborting");  
      return -1;  
   }  
  
   Console::WriteLine("Key/value pairs within 'Identities' key:");  
   array<String^>^ name = rk->GetValueNames( );  
   for (int i=0; i<name->Length; i++)  
   {  
      String^ value = rk->GetValue(name[i])->ToString();  
      Console::WriteLine("   {0} = {1}", name[i], value);  
   }  
  
   return 0;  
}  
```  
  
## Remarques  
 La classe <xref:Microsoft.Win32.Registry> est simplement un conteneur pour les instances statiques de <xref:Microsoft.Win32.RegistryKey>.  Chaque instance représente un nœud du Registre de la racine.  Les instances sont <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> et <xref:Microsoft.Win32.Registry.Users>.  
  
 En plus d'être statiques, les objets de la classe <xref:Microsoft.Win32.Registry> sont en lecture seule.  Par ailleurs, les instances de la classe <xref:Microsoft.Win32.RegistryKey> qui sont créées pour accéder au contenu des objets du Registre sont également en lecture seule.  Pour obtenir un exemple illustrant comment substituer ce comportement, consultez [Comment : écrire des données dans le Registre Windows](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).  
  
 Il existe deux objets supplémentaires dans la classe <xref:Microsoft.Win32.Registry> : <xref:Microsoft.Win32.Registry.DynData> et <xref:Microsoft.Win32.Registry.PerformanceData>.  Tous les deux sont des instances de la classe <xref:Microsoft.Win32.RegistryKey>.  L'objet <xref:Microsoft.Win32.Registry.DynData> contient des informations de Registre dynamiques prises en charge uniquement dans Windows 98 et Windows Millenium Edition.  L'objet <xref:Microsoft.Win32.Registry.PerformanceData> peut être utilisé pour accéder aux informations de compteur de performance pour les applications qui utilisent le Système d'analyse des performances de Windows.  Le nœud <xref:Microsoft.Win32.Registry.PerformanceData> représente des informations qui ne sont pas réellement stockées dans le Registre et qui ne peuvent donc pas être affichées à l'aide de Regedit.exe.  
  
## Voir aussi  
 [Comment : écrire des données dans le Registre Windows](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)