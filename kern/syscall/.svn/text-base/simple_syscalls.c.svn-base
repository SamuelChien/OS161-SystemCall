#include <kern/wait.h>
#include <types.h>
#include <lib.h>
#include <syscall.h>
#include <kern/errno.h>

/*Printchar
 *Input Argument: char c, the character you want to print
 *Return: integer 0 for success else handle with correct error number
 */
int printchar(char c)
{
	//Check if c exists, if not handle it with correct argument error
	if(c && c >= 0 && c < 127)
	{
		kprintf("%c", c);
		DEBUG(DB_SYSCALL, "System printchar successfully printed %c", c);
		//Here we actually return success value 0 bit shift 2 + 1
		return _MKWVAL(0) + 1;
	}
	else
	{
		DEBUG(DB_SYSCALL, "System printchar didn't print due to bad argument");
		return _MKWVAL(EINVAL) + __WEXITED;
	}
}
