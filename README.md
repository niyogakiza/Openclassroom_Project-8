# Openclassroom_Project-8
### Jasmine, JavaScript, Optimisation, Performance, Technical Documentation

Debug and Jasmine test
![ScreenShot](/P:8-OC/image/screen1.png)
![ScreenShot](/P:8-OC/image/screen2.png)
![ScreenShot](/P:8-OC/image/screen3.png)
![ScreenShot](/P:8-OC/image/screen4.png)

* Step 1: Fix the bugs
* Step 2: Add tests
* Step 3: Analyze performance
* Step 4: Write technical documentation


### To run the application
```npm
npm install
open index.html in any browser
```
##Example code
describe('routing', function () {

		it('should show all entries without a route', function () {
			var todo = {title: 'my todo'};
			setUpModel([todo]);

			subject.setView('');

			expect(view.render).toHaveBeenCalledWith('showEntries', [todo]);
		});

		it('should show all entries without "all" route', function () {
			var todo = {title: 'my todo'};
			setUpModel([todo]);

			subject.setView('#/');

			expect(view.render).toHaveBeenCalledWith('showEntries', [todo]);
		});

		it('should show active entries', function () {
			// TODO: write test
			var todo = {title: 'my todo', completed: false};
			setUpModel([todo]);

			subject.setView('#/active');
            expect(model.read).toHaveBeenCalledWith({completed:false}, jasmine.any(Function));
			expect(view.render).toHaveBeenCalledWith('setFilter', 'active');
			expect(view.render).toHaveBeenCalledWith('showEntries', [todo]);
		});

		it('should show completed entries', function () {
			// TODO: write test
			var todo = {title: 'my todo', completed:true};
			setUpModel([todo]);

			subject.setView('#/completed');
            expect(model.read).toHaveBeenCalledWith({completed:true}, jasmine.any(Function));
			expect(view.render).toHaveBeenCalledWith('setFilter', 'completed');
			expect(view.render).toHaveBeenCalledWith('showEntries', [todo]);
		});
	});
