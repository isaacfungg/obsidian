I ran the code for 5 hours with 4 x NVIDIA Tesla V100 32GB NVLink at a batch size of 64


The program I have updated it to tell me when it is attempting reaching each image and after 5 hours of running the code I got 255 000 lines of code which is around 182.6 epochs. The default number that UNeXt-pytorch has set in the GitHub was 500. This roughly converts to 36.4 epochs. So I would still need to either test the results with a smaller epoch value or have the code running for 14 hours.