# Termistor

## Propósito
  A biblioteca faz a conversão de n valores de adc de sensores térmicos em graus Célsius.

## Exemplo
```c

   float *temp_;
   static uint32_t value[3];     //registrador dos valores de adc
   HAL_ADC_Start_DMA(&hadc1, value, 3);  //start adc in dma mode with tree channels


	  temp_ = Temp_GetValue(value, 3);
   if(temp_[1]>30)
   {
		 HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
   }

```
## Documentação
 Como estão organizadas as funções?
A biblioteca contém uma única função, Temp_GetValue, onde os argumentos value e Lenght recebem o endereço do vetor com os valores em adc e o número de células para converção

## Notas
 Tem alguma coisa que é bom saber antes de usar a biblioteca?
 Os fatores B, To e Ro definidos na biblioteca são dados pelo fabricante, sendo To e Ro, uma peratura e resistencia específicas sobre o termistor.
