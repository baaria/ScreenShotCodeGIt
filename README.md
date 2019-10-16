# ScreenShotCodeGit

CPE 520 Fall 2019

This project explores how neural networks can be exploited to enhance front end development workflows and automate much of the repetitive work so that focus for developers can be on implementing functionality and improving efficiency. It builds off pix2code and screenshot2code.

Currently, design mockups created by designers are sent to front end developers who implement the mockup and then transform it into a fully functional site. This work can be cumbersome and time consuming and can end up taking away from many other parts of development that need attention. With an implementation of a neural network, this process can be streamlined. As Benjamin Wilkins says about Airbnb's [Sketching Interfaces:](https://airbnb.design/sketching-interfaces/) "The time required to test an idea should be zero."


### Implementation
This project uses the [pix2code](https://github.com/tonybeltramelli/pix2code/tree/master/model) dataset and an adapted version of the original neural network architecture of Emil Wallner's implementation. 

I trained using 2 different models, one which is the LSTM encoder decoder architecture used by Emil Wallner's [screenshot2code](https://github.com/emilwallner/Screenshot-to-code). This was very slow on a single GPU and consisted of nearly 140 million parameters. The other is a GRU encoder decoder architecture with additional max pooling layers, which dramatically decreases the amount of parameters by almost 70%. The network converged much faster, around 50 epochs, and still performed equivalently to the LSTM architecture. Both achieved a bleu score of about 50% and outputed similar code.


### Credits
##### Tony Baltramelli, Pix2Code
The dataset was provided by Tony Baltramelli of [pix2code](https://github.com/tonybeltramelli/pix2code/tree/master/model). Along with the dataset is the DSL he created for easy tokens and so I implemented a version of the compiler class he wrote as well, with minor changes to fix the parsing. 
##### Emil Wallner, screenshot2Code
The original LSTM architecture and code was from [screenshot2code's](https://github.com/emilwallner/Screenshot-to-code) bootstrap implementation of the neural network. I tweaked the code and network architecture as I experimented to improve efficiency and gather metrics. 

### Additional Projects to Check Out
Harvard's [im2markup](https://github.com/harvardnlp/im2markup): This would be an interesting dataset to train the model with.
[Machine Learning-Based Prototyping of GUI for Mobile Apps](https://arxiv.org/pdf/1802.02312.pdf)


