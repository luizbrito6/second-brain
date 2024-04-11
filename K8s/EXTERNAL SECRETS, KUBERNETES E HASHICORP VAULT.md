

1. Instalar o HELM 
2. A configuração do Vault em produção é diferente do mostrado no vídeo
	1. Instalar o vault da hashcorp com o helm
	2. importatne guardar os tokes de inicialização do vault em outro fora do cluster 
	3. Realizar o procedimento de inicialização do vault
	4. Baixar o vault diretamente pelo o apt (não entendi muito bem)
	5. Para acessar o vault status é necessário realizar uma configuração onde passamos a url com o clusterip do vault, com isso é necessário exportar a variável VAULT_ADDR, conseguimos o ip do vault com o seguinte comando (kubectl get svc)
	6. Agora começamos de fato o processo de inicialização (vault operator init) iimportante guardar os  tokens gerados. 
	7. Após isso é necessário quebrar o lacre do vault com os tokens gerados (valt)
	8. teste teste
	
		



