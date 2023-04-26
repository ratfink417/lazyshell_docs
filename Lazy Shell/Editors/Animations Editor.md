Animation scripts are all battle-oriented scripts which include all spell, attack, item, entrance, event, and behavior animations.  This includes all sprite behavior in battle--allies, monsters, spells, etc.

This editor is somewhat similar to the event scripts editor, but several distinctions must be made.
   
   1. The inability to add or delete commands to or from animation scripts, due to the complicated organization of the data into external rather than internal subroutines.
   
   2. The flow layout orientation of subroutines: event scripts are straightfoward and linear, while animation scripts are displayed as a multi-level tree where sub-routines are displayed as child nodes. Subroutines can be called multiple times in the same script, hence the fact that changing a command's properties can alter other nodes as well.
   
   3. A greater dependency on memory slots also contributes to the difficult nature of this editor. Different memory values can affect subsequent sub-routine pointers, such as the $68 or $64 command which relies on index pointers.
   
   4. Memory can be accessed as two types: AMEM (animation memory) and OMEM (object memory). AMEM is the primary memory type, accessible at all levels, while OMEM is linked to the current object, assigned by the $68 or $64 commands and accessible only in the synchronous object routine.
   
   - **Category:**  Select the animation script category.
   - **Animation Index:** Select the animation to load.
   - **Command Tree:** The collection of commands that comprise the animation script. Nodes are drawn in a hierarchical format for subroutines and animation packets used by the script. Check the nodes to move commands up or down--they cannot be delete, copied or pasted, however. Click a node to edit its properties in the panel on the right. Note that not all commands have been documented nor have their parameters been disassembled to a user-friendly GUI.
   - **Apply:**  Applies all changes made to the selected command.
   - **Empty:** Fills the animation opcode and parameters with 1-byte $0A NOOP commands. This can be used to "delete" a command or replace it with a new one.
   - **Apply:** Apply all changes made to the selected command's raw hex data.
   