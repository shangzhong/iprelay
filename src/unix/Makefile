###################################################################
#
#		ip_relay Makefile 
#		Vodoo Technologies ( Rachad 2003 -- ralao@venus.org )
#
###################################################################


all: ip_relay 

lib_ip_relay.a: ../lib_ip_relay.c
	gcc -c ../lib_ip_relay.c -o lib_ip_relay.o
	ar rcs lib_ip_relay.a lib_ip_relay.o
	gcc -c -fPIC ../lib_ip_relay.c -o lib_ip_relay_so.o
	gcc -shared -Wl,-soname,lib_ip_relay.so.1 -o lib_ip_relay.so.1.0.1 lib_ip_relay_so.o -lc


ip_relay: ../ip_relay.c lib_ip_relay.a
	gcc ../ip_relay.c lib_ip_relay.a -o ip_relay

clean:
	rm -f ip_relay.o lib_ip_relay.so.1.0.1 lib_ip_relay.a ip_relay

