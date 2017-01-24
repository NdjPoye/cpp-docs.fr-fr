---
title: "Comment&#160;: &#233;crire des donn&#233;es dans le Registre Windows (C++/CLI) | Microsoft Docs"
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
  - "Registre, écrire dans"
  - "Visual C++, écrire dans le registre Windows"
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;crire des donn&#233;es dans le Registre Windows (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant utilise la clé <xref:Microsoft.Win32.Registry.CurrentUser> pour créer une instance accessible en écriture de la classe <xref:Microsoft.Win32.RegistryKey> qui correspond à la clé **Software**.  La méthode <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> est ensuite utilisée pour créer une nouvelle clé et l'ajouter aux paires clé\/valeur.  
  
## Exemple  
  
### Code  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## Remarques  
 Vous pouvez utiliser le .NET Framework pour accéder au Registre avec les classes <xref:Microsoft.Win32.Registry> and [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx) qui sont toutes les deux définies dans l'espace de noms <xref:Microsoft.Win32>.  La classe **Registry** est un conteneur pour les instances statiques de la classe <xref:Microsoft.Win32.RegistryKey>.  Chaque instance représente un nœud du Registre de la racine.  Les instances sont <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> et <xref:Microsoft.Win32.Registry.Users>.  
  
## Voir aussi  
 [Comment : lire les données du Registre Windows](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)