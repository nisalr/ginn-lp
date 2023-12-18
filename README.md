This code is an implementation of the paper "GINN-LP: A Growing Interpretable Neural Network for Discovering Multivariate Laurent Polynomial Equations".

# Quick Start

This package can be installed using pip locally.

    pip install -U ./symnn
  
After installing the package, you can use the scikit-learn compatible API to fit the model and generate output predictions. The default hyperparameters are listed below.

    from symnn.sym_nn import SymNN
    est = SymNN(reg_change=0.5,
            start_ln_blocks=1,
            growth_steps=3,
            l1_reg=1e-4,
            l2_reg=1e-4,
            num_epochs=500,
            round_digits=3,
            train_iter=4)
    est.fit(train_x, train_y)
    
Here, train_x should be a pandas dataframe object or numpy array containing input features. train_y should be a pandas series, dataframe or a numpy array containing target values.

Once the model is trained, the recovered mathematical equation can be viewed by,

    print(est.recovered_eq)
    
Here, the recovered_eq variable contains a SymPy expression.
