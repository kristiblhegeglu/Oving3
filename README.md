Oving3
======

TCP


#include <stdio.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netinet/in.h>
#include <netdb.h>

//Client
/*
const struct sockaddr {
	char iPAdress;
	int port;
};
*/
int main(){

	int sockfd,n;
	struct sockaddr_in servaddr;
	char sendline[1000];
	char recvline[1000];

	sockfd=socket(AF_INET,SOCK_STREAM,0);

	bzero(&servaddr,sizeof(servaddr));
	servaddr.sin_family = AF_INET;
	servaddr.sin_addr.s_addr=inet_addr("129.241.187.161");
	servaddr.sin_port=htons(33546);

	connect(sockfd, (struct sockaddr *)&servaddr, sizeof(servaddr));

/*
	int sock;
	sock = socket(AF_INET, SOCK_STREAM, 0);




	struct sockaddr serv_addr;
	serv_addr.iPAdress = 129.241.187.161;
	serv_addr.port = 33546;


	sock.connect(sock,struct sockaddr, 15);

	return 0;
*/
}

