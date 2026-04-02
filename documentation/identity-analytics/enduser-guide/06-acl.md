---
title: "Identity Analytics Enduser Guide"
description: "Identity Analytics Enduser Guide"
---

# ACLs definitions  

Access rights to **Shares** and **Shared folders** are displayed in IAS/IAP as Access Control Lists (ACLs). ACLs can be shown in three different ways:

- **Simplified ACLs** – for quick, easy understanding, especially for business users  
- **Basic ACLs** – mapping to Microsoft Windows permissions as shown in the Windows GUI  
- **Advanced ACLs** – for expert users who need full detail  

In most tables, simplified ACLs are used. On share and folder detail pages or in detail windows, the end user can switch to basic ACLs and, if needed, display advanced ACLs.  

The sections below define each ACL display option.

## Simplified ACLs

| **Simplified ACLs** | **Label**        |
| :-----------------: | :--------------- |
| R                   | Read             |
| W                   | Write (Windows)  |
| C                   | Total Control    |

## Basic ACLs

| **Basic ACLs** | **Label**                      | **Advanced ACLs corresponding**               |
| :------------: | :---------------------------- | :-------------------------------------------- |
| R              | Read (Windows)                | RGFE                                          |
| W              | Write (Windows)               | WGAML                                         |
| X              | Read and Execute /            | RXGFE                                         |
| X              | List Folder Content (Windows) | RXGFE                                         |
| M              | Modify (Windows)              | RWXGAFEMDL                                    |
| F              | Full Control (Windows)        | RWXGASPFEMDL                                  |
| S              | Special (Windows)             | Any combination not matching any of the above |
| L              | Read (Identity Analytics)     | R                                             |
| U              | Update (Identity Analytics)   | WAMLDS                                        |
| C              | Control (Identity Analytics)  | PO                                            |

## Advanced ACLs

| **Advanced ACLs** | **Label**                         | **Description**                                                                                           |
| :---------------: | :--------------------------------- | :-------------------------------------------------------------------------------------------------------- |
| R                 | List folder or Read file          | Data can be read from the file, or the folder contents can be listed.                                     |
| W                 | Create files or Write data        | Data can be written to the file, or new files can be created in the folder.                               |
| X                 | Traverse folder or Execute file   | Data can be read into memory from the file using system paging I/O.                                       |
| G                 | Read permissions                  | The ACL and ownership associated with the file can be read.                                               |
| A                 | Create folders or Append data     | Data can be appended to the file, or subfolders can be created in the folder.                             |
| S                 | Delete subfolders and files       | Files and empty folders in this shared folder can be deleted, even without delete rights on the folder.   |
| P                 | Change permissions                | The ACL and ownership associated with the file can be modified.                                           |
| F                 | Read extended attributes          | Extended attributes associated with the file can be read.                                                 |
| O                 | Take ownership                    | Ownership information associated with the file can be modified.                                           |
| E                 | Read attributes                   | Standard attributes associated with the file can be read.                                                 |
| M                 | Write extended attributes         | Extended attributes associated with the file can be modified.                                             |
| D                 | Delete                            | The file can be deleted.                                                                                  |
| L                 | Write attributes                  | Standard attributes associated with the file can be modified.                                             |
