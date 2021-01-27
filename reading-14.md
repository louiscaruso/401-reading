## Read: Class 14 ##

### Matplotlib ###


- Simple plot:
    - First step to get the data for the sine and cosine functions:
        
        - import numpy as np
        X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
        C, S = np.cos(X), npsin(X)

    
- Plotting several lines with different format style in one function

        import numpy as np
        # evenly sampled time at 200ms intervals
        t = np.arange(0, 5, 0.2)
        # red dashes, blue squares and green triangles
        plt.plot(t, t, 'r--', t, t**2, 'bs' , t, t**3, 'g^')
        plt.show()


![Alt text](Screenshot11.png)



- Matplotlib allows you provide such an object with the data keyword argument. If provided, then you may generate plots with the strings corresponding to these variables.

        data = {'a': np.arange(50),
                'c': np.random.randint(0, 50, 50),
                'd': np.random.randn(50)}
        data['b'] = data['a'] + 10 * np.random.randn(50)
        data['d'] = np.abs(data['d']) * 100

        plt.scatter('a', 'b', c='c', s='d', data=data)
        plt.xlabel('entry a')
        plt.ylabel('entry b')
        plt.show()


- Plotting with categorical variables

        names = ['group_a', 'group_b', 'group_c']
        values = [1, 10, 100]

        plt.figure(figsize=(9, 3))

        plt.subplot(131)
        plt.bar(names, values)
        plt.subplot(132)
        plt.scatter(names, values)
        plt.subplot(133)
        plt.plot(names, values)
        plt.suptitle('Categorical Plotting')
        plt.show()


    - Controlling line properties"

        - use keyword args:
            plt.plot(x, y, linewidth=2.0)

        - setter method of Line2D instance.plot
            line, = plt.plot(x, y, '-')
            line.set_antialiased(False) # turn off antialiasing

        - use setp.

            lines = plt.plot(x1, y1, x2, y2)
            # use keyword args
            plt.setp(lines, color='r', linewidth=2.0)
            # or MATLAB style string value pairs
            plt.setp(lines, 'color', 'r', 'linewidth', 2.0)

        

- Working with multiple figures and axes
           def f(t):
            return np.exp(-t) * np.cos(2*np.pi*t)

        t1 = np.arange(0.0, 5.0, 0.1)
        t2 = np.arange(0.0, 5.0, 0.02)

        plt.figure()
        plt.subplot(211)
        plt.plot(t1, f(t1), 'bo', t2, f(t2), 'k')

        plt.subplot(212)
        plt.plot(t2, np.cos(2*np.pi*t2), 'r--')
        plt.show() 

![Alt text](Screenshot12.png)

