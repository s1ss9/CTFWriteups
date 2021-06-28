## Category

Crypto

## Challenge

Decrypt the given data:

    GHTr!h}DeChisa C D!p_t  bDstn_ ieC_i0h ss230t@  t1nn_r t!{c_td 

300 points

## Hint(s)

None used

## Solution

The string looks random at first but notice that all the elements of the flag format (such as C, D, 2, 1, '{', '}') are already part of the string, only out of order. 

While trying to decipher the order, we realise that each of the character in 'CDDC21{' are in order, just separated by other characters. Some counting reveals that their spacing are equal (8 chars).

As such, we write a simple python program to cycle through and string and extract every 8 character starting from the first 'C'.

    text = "GHTr!h}DeChisa C D!p_t  bDstn_ ieC_i0h ss230t@  t1nn_r t!{c_td "

    index = 9  #First 'C'
    while True:
      print(text[index], end='')
      index = (index+8)%len(text)
      
The output we get is "DC is tGe best!HCDDC21{Th!s_3ncripti0n_!s_n0t_that_h@rd}"

## Flag

    CDDC21{Th!s_3ncripti0n_!s_n0t_that_h@rd}
